# check_ssl.py - Check expiration of SSL certificates for your services

**check_ssl.py** can check time for expiration in days of your server certificates.
Also, it can check _commonName_ and _SubjectAltName_ for validation and testing purposes.
It implements [SNI](https://en.wikipedia.org/wiki/Server_Name_Indication), so multiple virtualhosts are supported.

**Works only in Python 3.x**

To run, edit check_ssl.py and tune following parameters in config{}:

* **host**: FWDN which will be invocated
* **port**: Port where TLS connection is listening. If not set, defaults to 443
* **critical:** Days to expiration, set as critical. If not set, defaults to 5
* **warning:** Days to expiration, set as warning. If not set, defaults to 15
* **cn:** Canonical name which is expected in certificate. If not set, defaults to "host" parameter. Will be checked
against all commonName and SubjectAltNames present in certs.

### TODO:

- Let user define TLS/SSL version protocol to use. TLSv1_1 is used now
- Parseable format output, perhaps JSON