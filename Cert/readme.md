# gen cert 

```bash
mkdir -p ./certs &&  openssl req -x509 -nodes -days 365 \
-newkey rsa:2048 \
-subj "/C=CN/ST=HB/L=WH/O=baidu/OU=dev/CN=cert@baidu.com/emailAddress=cert@baidu.com" \
-keyout ./privkey.pem \
-out ./cert.crt

openssl pkcs12 -export -in cert.crt -inkey privkey.pem -out proxy1.p12 -name "MITM C++ Certificate" -passout pass:
```