# Spiffe Support and Examples

The **spiffe-support** directory contains source code for SPIFFE support in
nginx, as well as some example nginx configurations.

## SPIFFE Support Source Code

+ See the [src](src) directory.

## nginx Example Configurations

Example configurations for two types of deployments are provided to illustrate
proxying traffic from one nginx server to another using mTLS. One example is for
proxying HTTP traffic, another for proxying via a TCP tunnel.

### HTTP Proxy

These example configurations are for proxying HTTP traffic between two nginx
servers via mTLS.

+ [nginx_fe.conf](nginx_fe.conf) acts as an mTLS client, proxying traffic to
  the "blog" server.
+ [nginx_blog.conf](nginx_blog.conf) is the web server hosting the proxied
content.

### TCP Proxy

The TCP examples work similar to the HTTP Proxy examples, only instead of
proxying HTTP traffic, a TLS tunnel is used via the nginx streams module. This
can be used to proxy generic TCP traffic such as a database connection.

+ [nginx_tcp_frontend.conf](nginx_tcp_frontend.conf) is the client configuration
  which proxies to the backend via mTLS.
+ [nginx_tcp_backend.conf](nginx_tcp_backend.conf) contains server configuration
  which proxies client connections to a backend service (such as a database) via
  mTLS.
