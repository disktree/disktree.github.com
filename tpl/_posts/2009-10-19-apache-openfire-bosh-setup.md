---
layout: post
title: Apache-Openfire BOSH setup
---
For BOSH usage, you have to connect your client to the http address of your jabber server.  
Default on openfire is: http://localhost:7070/http-bind/  
<br>
Your apache server doesn’t know about your jabber server, so you have to setup a proxy to forward requests:  
http://localhost/jabber/ > http://localhost:7070/http-bind/  
<br>
Activate the mod_proxy apache module  
<pre class="code">
sudo ln /etc/apache2/mods-available/proxy.load /etc/apache2/mods-enabled
</pre>
<br>
Activate the mod_proxy apache module  
<pre class="code">
sudo ln /etc/apache2/mods-available/proxy.load /etc/apache2/mods-enabled
</pre>
<br>
Add following line to proxy.load for loading the module
<pre class="code">
LoadModule proxy_http_module /usr/lib/apache2/modules/mod_proxy_http.so
</pre>
<br>
Add the proxy directive to the host settings in your http.conf
<pre class="code">
ProxyRequests Off
ProxyPass /jabber http://localhost:7070/http-bind/
ProxyPassReverse /jabber http://localhost:7070/http-bind/
ProxyPass /jabbers http://localhost:7443/http-bind/
ProxyPassReverse /jabbers http://localhost:7443/http-bind/
</pre>
<br>
Restart apache
<pre class="code">
sudo /etc/init.d/apache2 restart
</pre>
<br>
Using [HXMPP](http://hxmpp.disktree.net), you can now create a connection by passing in the path in the constructor, like: 
<pre class="code haxe">var cnx = new BOSHConnection( "myjabberserver.net", "127.0.0.1/jabber/" );</pre>
