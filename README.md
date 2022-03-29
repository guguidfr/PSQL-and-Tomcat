# PSQL-and-Tomcat
Funciona correctamente en CentOS 7.
## Acerca del rol:
Este rol creará:
- Un servidor de base de datos PostgreSQL que creará al usuario "postgres" (default psswd: postgres).
- Un servidor Tomcat accesible desde mediante interfaz web con el puerto 8080
## Cómo usar el rol:
- Clona el proyecto:
```
git clone https://github.com/guguidfr/PSQL-and-Tomcat/tree/main
cd PSQL-and-Tomcat
```
- Edita el archivo de hosts:
```
vim hosts
[server]
192.168.1.25
```
- Edita los credenciales del servidor de Tomcat:
```
vim roles/tomcat/vars/main.yml
ui_manager_user: manager                    # Usuario para acceder desde la interfaz web
ui_manager_pass: Str0ngManagerP@ssw3rd      # Contraseña del usuario de la interfaz web
ui_admin_username: admin                    # Usuario administrador
ui_admin_pass: Str0ngAdminP@ssw3rd          # Contraseña del administrador
```
- Ejecuta el playbook:
```
ansible-playbook start.yml
```
# Créditos:
El rol de creación del servidor de base de datos lo he creado yo mismo a partir de una guía en:
```
https://computingforgeeks.com/how-to-manage-postgresql-database-with-ansible/
```
El rol de creación del servidor Tomcat es a partir del proyecto de @jmutai:
```
https://github.com/jmutai/tomcat-ansible
```
