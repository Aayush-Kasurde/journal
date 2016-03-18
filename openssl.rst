OpenSSL
=======


* View Certificate Request using openssl ::
    
    $ openssl req -in mycsr.csr -noout -text


* Create new Certificate request with new key ::


    $ openssl req -nodes -newkey rsa:2048 -keyout example.key -out example.csr -subj "/C=GB/ST=London/L=London/O=Global Security/OU=IT Department/CN=example.com"


* Create new Certificate request with existing key :: 
    
    $ openssl req -new -key example.key -out example.csr -subj "/C=GB/ST=London/L=London/O=Global Security/OU=IT Department/CN=example.com"

* View p12 file ::
	
    $ openssl pkcs12 -info -in keyStore.p12

