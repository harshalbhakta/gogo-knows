
<img src="https://github.com/images/error/angry_unicorn.png" alt="Drawing" style="width: 75px;"/> NGINX + Unicorn
===
----

Introduction
----
<br />
**Nginx** 

It is a pure web server that's intended for serving up static content and/or redirecting the request to another socket to handle the request.

**Unicorn** 

It is a Rack web server and only intended to host a 'Rack App' which is usually generating dynamic content. Rack apps can also serve up static content but it's less efficient than most other traditional web servers. 

It is an HTTP server for Rack applications designed to only serve fast clients on low-latency, high-bandwidth connections and take advantage of features in Unix/Unix-like kernels. Slow clients should only be served by placing a reverse proxy capable of fully buffering both the the request and response in between Unicorn and slow clients. - [http://unicorn.bogomips.org/](http://unicorn.bogomips.org/)

Common Setup
----
<br />
Most RoR setups use a combination of both traditional web servers and Rack servers to apply the best of both of their capabilities. Nginx is incredibly fast at request redirection through proxy balancing and serving up static content. Unicorn is quite capable of processing HTTP headers and balancing inbound requests to Ruby for processing.

Sources
----

* [http://stackoverflow.com/a/8753332](http://stackoverflow.com/a/8753332)
* [http://unicorn.bogomips.org](http://unicorn.bogomips.org)
* [http://wiki.nginx.org/Main](http://wiki.nginx.org/Main)