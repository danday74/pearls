# nmap

This linux command outputs SSL cipher strengths and warnings when executed against a running web server.

## Installation

Install nmap from https://nmap.org/download.html

1. wget the tar ( ATOW wget https://nmap.org/dist/nmap-7.12.tar.bz2 )

2. Follow the compile-it-yourself instructions on the nmap website.

## Execute

nmap --script ssl-enum-ciphers -p 443 localhost

## Notes

Do not use SSLv3, TLSv1.1 & 1.2 should be available.

Cipher suites should not be weak (Grade B and C).

Tweak webserver config to correct these then restart server and run nmap again.

Example Apache config.

```
# SSL Engine Switch:
# Enable/Disable SSL for this virtual host.
SSLEngine on
SSLProtocol -All +SSLv3 +TLSv1
SSLHonorCipherOrder On
SSLCipherSuite ECDHE-RSA-AES256-SHA384:AES256-SHA256:RC4:HIGH:!MD5:!aNULL:!EDH:!AESGCM
```

## Related articles

https://hynek.me/articles/hardening-your-web-servers-ssl-ciphers

https://raymii.org/s/tutorials/Strong_SSL_Security_On_Apache2.html
