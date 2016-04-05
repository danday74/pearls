# pearls
Pearls of knowledge

# nmap
install nmap from https://nmap.org/download.html with ...

1 - wget the tar ( ATOW wget https://nmap.org/dist/nmap-7.12.tar.bz2 )

2 - Follow the compile-it-yourself instructions

3 - nmap --script ssl-enum-ciphers -p 443 localhost

This outputs cipher strengths and warnings. Tweak webserver config to correct these.
Example Apache config.

```
# SSL Engine Switch:
# Enable/Disable SSL for this virtual host.
SSLEngine on
SSLProtocol -All +SSLv3 +TLSv1
SSLHonorCipherOrder On
SSLCipherSuite ECDHE-RSA-AES256-SHA384:AES256-SHA256:RC4:HIGH:!MD5:!aNULL:!EDH:!AESGCM
```

Do not use SSLv3, TLSv1.1 & 1.2 should be available.

Cipher suites shouldn't be weak (Grade B and C).

https://hynek.me/articles/hardening-your-web-servers-ssl-ciphers/

https://raymii.org/s/tutorials/Strong_SSL_Security_On_Apache2.html
