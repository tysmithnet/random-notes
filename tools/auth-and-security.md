# Auth/Security
20220221144831

#tool #auth #security

Tools related to auth, security, SSL, JWT etc

### minica 
#minica #ssl #certificate #golang #cli #development

> Minica is a simple CA intended for use in situations where the CA operator also operates each host where a certificate will be used. It automatically generates both a key and a certificate when asked to produce a certificate. It does not offer OCSP or CRL services. Minica is appropriate, for instance, for generating certificates for RPC systems or microservices.

- [github](https://github.com/jsha/minica)

### nslookup
#nslookup #activedirectory #microsoft #dns #cli

#### Find domain controller
This uses the interactive mode of nslookup

```
nslookup
> set type=all
>_ldap._tcp.dc._msdcs.DOMAINNAMEGOESHERE
```

