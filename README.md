# Nginx-proxy-demo

### Prepration for Services
`docker build . -t nodeapp`

`docker run --hostname nodeapp1 --name nodeapp1 -d nodeapp`

`docker run --hostname nodeapp2 --name nodeapp2 -d nodeapp`

`docker run --hostname nodeapp3 --name nodeapp3 -d nodeapp`

# Proxy
#### Layer 7

`docker run --hostname ng1 --name ng1 -p 80:8080 -v $(pwd)/nginx.conf:/etc/nginx/nginx.conf -d nginx`


`docker network create backendnet`

`docker network connect backendnet nodeapp1`

`docker network connect backendnet nodeapp2`

`docker network connect backendnet nodeapp3`

`docker network connect backendnet nginx`
#### Layer 4

`docker run --hostname ng1 --name ng1 -p 80:8080 -v $(pwd)/tcp.conf:/etc/nginx/nginx.conf -d nginx`


### Add SSL Certificate
[TODO]
### Support HTTP2

[TODO]

### Web Sockets

[TODO]
