---
layout: post
title: Flash policy nekoVM server written in neko
---
A simple flash-policy-server written in neko, for all minimalists.
<pre class="code">

i32_new = $loader.loadprim( "std@int32_new", 1 );
i32_to_int = $loader.loadprim( "std@int32_to_int", 1 );
host_resolve = $loader.loadprim( "std@host_resolve", 1 );
regexp_new = $loader.loadprim( "regexp@regexp_new", 1 );
regexp_match = $loader.loadprim( "regexp@regexp_match", 4 );
socket_new = $loader.loadprim( "std@socket_new", 1 );
socket_bind = $loader.loadprim( "std@socket_bind", 3 );
socket_listen = $loader.loadprim( "std@socket_listen", 2 );
socket_close = $loader.loadprim( "std@socket_close", 1 );
socket_recv = $loader.loadprim( "std@socket_recv", 4 );
socket_write = $loader.loadprim( "std@socket_write", 2 );
socket_peer = $loader.loadprim( "std@socket_peer", 1 );
host_to_string = $loader.loadprim( "std@host_to_string", 1 )


default_host = "127.0.0.1";
default_filepath = "flashpolicy.xml";
default_port = 843;


// READ CMD ARGS
args = $loader.args;
host = if( args[0] != null ) args[0] else default_host;
port = if( args[1] != null ) $int( args[1] ) else default_port;
filepath = if( args[2] != null ) args[2] else default_filepath;


// READ POLICY FILE
try 
	policyfile = $loader.loadprim( "std@file_contents", 1 )( filepath )
catch e {
	$print( "Cannot find policyfile at: " + filepath );
}
if( regexp_match( regexp_new( "cross-domain-policy" ), policyfile, 0, $ssize( policyfile ) ) == false ) {
	$print( "Invalid policy file: "+filepath+"\n" );
}


// RUN SERVER

$print( "Starting flash-policy server ...\n" );

socket = socket_new( false );
socket_bind( socket, i32_new( host_resolve( host ) ), port );
socket_listen( socket, 10 );

while( true ) {

	client = $loader.loadprim( "std@socket_accept", 1 )( socket );
	info = $loader.loadprim( "std@socket_peer", 1 )( client );
	ip = $array( host_to_string( info[0] ), info[1] );
	
	buf = $smake( 23 );
	try
		numbytes = socket_recv( client, buf, 0, $ssize( buf ) )
	catch e {
		$print(e);
	}
	input = $ssub( buf, 0, numbytes-1 );
	if( input != "<policy-file-request/>" ) {
		$print( "Invalid request from: "+ip+"\n" );
		try socket_write( client, "FuckYou\n" ) catch e {}
		socket_close( client );
	} else {
		try socket_write( client, policyfile ) catch e {}
		try $loader.loadprim( "std@socket_send_char", 2 )( client, 0 ) catch e {}
		socket_close( client );
		$print( "Policy sent to: "+ip+"\n" );
	}
}

</pre>
[fpserver.neko](/file/flashpolicyd.neko)
