# nginxtls
Minimal NGiNX static site with TLS


## Instructions
- Generate the server cert with these commands:
```shell
mkdir certs
openssl ecparam -genkey -name secp521r1 -out certs/server.key
openssl req -new -sha512 -key certs/server.key -out certs/server.csr
openssl req -x509 -sha512 -days 3650 -key certs/server.key -in certs/server.csr -out certs/server.crt
```
- Feel free to use your own cert
- Install docker-compose
- Run `docker build -t nginxtls .`
- Run `docker-compose up`
- Open your browser at https://localhost:3000
