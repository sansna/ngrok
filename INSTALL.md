Installing notes
=
Install golang, get this repo by go get github.com/sansna/ngrok.
cd into $GOPATH/src/github.com/sansna/ngrok, compile by:
```
GOOS="" GOARCH="" make release-client release-server
```
where GOOS and GOARCH selections can be find.

Also, to make it actually safe, you need to generate your own RSA keys and
certificates. When building client side binaries, the rootCA.pem file should
be put inside asset/client/tls/ ending with .crt.

Running your own server ngrokd with proper lines as:
```
bin/ngrokd -tlsKey=device.key -tlsCrt=device.crt -domain="$NGROK_DOMAIN" -httpAddr=":8000" -httpsAddr=":8001"
```

Look [here](https://gist.github.com/lyoshenka/002b7fbd801d0fd21f2f) for instructions about how to generate certificates.
