restore-ldap
============

Función
-------

Permite realizar una restauración de la configuración y/o la B.D. LDAP utilizando los backups
creados mediante el script backup-ldap

El script backup-ldap realiza un backup completo de LDAP con configuración OLC:  
* LDAP config (slapcat -n 0)
* LDAP DIT (slapcat -n 1)  
  
Los backups se guardan en el directorio /var/backups/ con nombres:
* backup-config-ldap-$TIMESTAMP.ldif
* backup-db-ldap-$TIMESTAMP.ldif  

Instalación
-----------

La forma más sencilla de instalarlo es ejecutar estos comandos en el servidor ldap:

   * wget --no-check-certificate -O /usr/local/sbin/restore-ldap https://raw.githubusercontent.com/algodelinux/restore-ldap/master/restore-ldap && chmod 755 /usr/local/sbin/restore-ldap  
  

Uso                   
---

   * restore-ldap [-h|--help]  
   * restore-ldap [-c|--config] backup-config-ldap-file [-d|--data] backup-data-ldap-file  

Ejemplos:  
   * restore-ldap -h  
   * restore-ldap --help  
   * restore-ldap -c backup-config-ldap-20170222.ldif  
   * restore-ldap -d backup-data-ldap-20170222.ldif  
   * restore-ldap -c backup-config-ldap-20170222.ldif -d backup-data-ldap-20170222.ldif  

## Authors

- Esteban M. Navas Martín (algodelinux@gmail.com)

