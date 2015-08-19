Certificate
============

Encodings (also used as extensions)
-----------------------------------

    - .DER 
      = The DER extension is used for binary DER encoded certificates. These files may also bear the CER or the CRT extension.   Proper English usage would be “I have a DER encoded certificate” not “I have a DER certificate”.

    - .PEM 
      = The PEM extension is used for different types of X.509v3 files which contain ASCII (Base64) armored data prefixed with a “—– BEGIN …” line.


Common Extensions
------------------

    - .CRT 
      = The CRT extension is used for certificates. The certificates may be encoded as binary DER or as ASCII PEM. The CER and CRT extensions are nearly synonymous.  Most common among *nix systems

    - .CER 
      = alternate form of .crt (Microsoft Convention) You can use MS to convert .crt to .cer 
      
    - .KEY 
      = The KEY extension is used both for public and private PKCS#8 keys. The keys may be encoded as binary DER or as ASCII PEM.


* List all certificates in current directory ::
    
    $ certutil -L -d .

* View PEM encoded certificate :: 
    
    $ openssl x509 -in cert.pem -text -noout
    $ openssl x509 -in cert.crt -text -noout
    $ openssl x509 -in cert.cer -text -noout


* Converting encoding from PEM to DER ::
    
    $ openssl x509 -in cert.crt -outform der -out cert.der

* Converting encoding from DER to PEM ::
    
    $ openssl x509 -in cert.crt -inform der -outform pem -out cert.pem


* Create p12 from certificate and key :: 
    
    $ openssl pkcs12 -export -out server.p12 -inkey server.key -in server.crt -certfile CACert.crt
