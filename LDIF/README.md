##### 以下をpasswd.ldifのolcRootPWへ記述
  ```$ slappasswd```

    {SSHA}aerganeroigajreg

##### update slappasswd
  ```# ldapadd -Y EXTERNAL -H ldapi:// -f ./LDIF/passwd.ldif```

    SASL/EXTERNAL authentication started
    SASL username: gidNumber=1000+uidNumber=1000,cn=peercred,cn=external,cn=auth
    SASL SSF: 0
    modifying entry "olcDatabase={0}config,cn=config"

##### change doamin
  ```# ldapmodify -x -D cn=config -w secret -f LDIF/chdomain.ldif```

    modifying entry "olcDatabase={1}monitor,cn=config"
    modifying entry "olcDatabase={2}hdb,cn=config"
    modifying entry "olcDatabase={2}hdb,cn=config"
    modifying entry "olcDatabase={2}hdb,cn=config"

##### update base
  ```# ldapadd -x -D "cn=Manager,dc=lazyarea,dc=com" -w secret -f ./LDIF/base.ldif```

    adding new entry "dc=lazyarea,dc=com"
    adding new entry "ou=People,dc=lazyarea,dc=com"
    adding new entry "ou=Group,dc=lazyarea,dc=com"
