---
layout: post
title: Apache/Openfire BOSH setup
---

Since HXMPP supports BOSH connections (flash/js) it’s time to write a little setup instruction….
In my (local) case for apache2/openfire 3.6.4 on ubuntu 9.04.
What has to be done is to be able to connect your client to the BOSH adress of your jabber server. Default on openfire is http://localhost:7070/http-bind/

Your apache server doesn’t know about your jabber server, so you have to setup a proxy to forward requests:
http://localhost/jabber/ > http://localhost:7070/http-bind/

Here we go:

#Activate the mod_proxy apache module if required
sudo ln /etc/apache2/mods-available/proxy.load /etc/apache2/mods-enabled

#Add following line to proxy.load for loading the module
LoadModule proxy_http_module /usr/lib/apache2/modules/mod_proxy_http.so

#Add the proxy directive to the host settings in your http.conf
ProxyRequests Off
ProxyPass /jabber http://localhost:7070/http-bind/
ProxyPassReverse /jabber http://localhost:7070/http-bind/
ProxyPass /jabbers http://localhost:7443/http-bind/
ProxyPassReverse /jabbers http://localhost:7443/http-bind/

#Restart apache
sudo /etc/init.d/apache2 restart

Thats it!
Using HXMPP, you can now create a connection by passing in the path in the constructor, like:
var cnx = new BOSHConnection( “myjabberserver.net”, “127.0.0.1/jabber/” );
