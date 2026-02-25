# SERVICIOS DE DOMINIO
Seguiremos estos pasos para instalar OpenLDAP en un servidor Linux:
- Instalamos un servidor Linux dentro de nuestra maquinas y ponemos el siguiente comando para instalarlo:

<img width="723" height="257" alt="imagen" src="https://github.com/user-attachments/assets/9ff57608-48f6-4eee-a8fc-d7f32542a681" />

- Se nos abrira un menu para poner la contraseña y lo ponemos para que termine la instalacion.
- Antes de nada, hay que usar el comando "sudo nano /etc/hosts" y poner la IP de nuestro servidor.

<img width="580" height="227" alt="imagen" src="https://github.com/user-attachments/assets/f409421a-2067-4ea0-82df-a42a4b16d0ee" />


- Tambien editamos el directorio Netplan y lo configuramos de la siguiente manera:

<img width="343" height="173" alt="imagen" src="https://github.com/user-attachments/assets/1dcbc995-cd79-40cd-9efe-c73763cb4324" />

- Miramos con el comando "dpkg –L slapd | grep (cualquier archivo)" para mirar dentro del archivo que nos ha creado la instalacion por el nombre que le pongamos, destacandolos con color por el -L.

<img width="600" height="318" alt="imagen" src="https://github.com/user-attachments/assets/76990564-2029-4408-bfdf-b69021dc57c7" />
<img width="600" height="782" alt="imagen" src="https://github.com/user-attachments/assets/419b3831-b297-4d0a-bf90-204053848d2e" />
<img width="602" height="177" alt="imagen" src="https://github.com/user-attachments/assets/c4e16ae1-e3f0-4ffa-8610-51dc07e0cfdd" />
<img width="602" height="785" alt="imagen" src="https://github.com/user-attachments/assets/d31c9f94-f219-42dc-b612-fbf5fbe902b8" />

- Activamos el archivo de configuracion del servidor LPAD y cuando salga la pantalla de ello le damos a no. Una vez hecho le tenemos que poner nombre al dominio.

<img width="954" height="280" alt="imagen" src="https://github.com/user-attachments/assets/61c7537f-23cc-4649-acbf-6040d43703b6" />

-Le ponemos un nombre de organizacion.

<img width="729" height="280" alt="imagen" src="https://github.com/user-attachments/assets/4e9c759b-738a-44c5-b0e0-f9f2d4606767" />

- Una vez puesta la contraseña, en este menu ponemos no.

<img width="638" height="203" alt="imagen" src="https://github.com/user-attachments/assets/593a63fb-d743-491d-a27f-8fff880753ec" />

- Y aqui le damos que si para que cree una nueva base de datos.

<img width="940" height="203" alt="imagen" src="https://github.com/user-attachments/assets/20b31d29-d08e-40f4-8fd9-ed202e4651f7" />

- Una vez ya esto, con el servidor podemos poner estos comandos:

<img width="1014" height="263" alt="imagen" src="https://github.com/user-attachments/assets/44e7163a-59cc-4aa5-8555-a51928b03f65" />

- Creamos un grupo de configuracion llamado "grupo.ldif" y ponemos lo siguiente:

<img width="354" height="201" alt="imagen" src="https://github.com/user-attachments/assets/d4ad4c7b-3fc7-4dfb-8ec0-f71f651a125c" />

- Y añadimos el usuario que queriamos a este

<img width="899" height="91" alt="imagen" src="https://github.com/user-attachments/assets/a34a371c-2f10-44e1-b252-5ed03a7e8f3f" />

- Creamos otro .ldif para los usuarios

<img width="506" height="225" alt="imagen" src="https://github.com/user-attachments/assets/09f44e0b-bcff-4050-a209-32325805659c" />

- Y añadimos el usuario a este tambien

<img width="917" height="63" alt="imagen" src="https://github.com/user-attachments/assets/b154abee-3d6c-4b23-a304-7a79dbf9f027" />

- En el archivo "usuarios.ldif" hay que poner tambien esto para que tenga una contraseña.

<img width="191" height="18" alt="imagen" src="https://github.com/user-attachments/assets/a5fd7a24-1686-4f4d-99e7-fb377e453f5c" />

- Con el comando "ldapsearch" podemos ver el arbol en que estan los usuarios que hemos creado

<img width="876" height="172" alt="imagen" src="https://github.com/user-attachments/assets/fd0d8562-68e9-46e8-9b43-dcdcfdfdcd65" />

## INSTALACION DE PHPLDAPADMIN (TAMBIEN EN FORMA GRAFICA)
- Usamos este comando para instalarlo:

<img width="947" height="226" alt="imagen" src="https://github.com/user-attachments/assets/654befeb-5a60-46a4-a7f5-827af1499436" />

- Una vez instalado, entramos dentro de "/usr/share/phpldapadmin/config/config.php" y editamos lo siguiente:

<img width="586" height="69" alt="imagen" src="https://github.com/user-attachments/assets/6bda1793-fba2-4ed3-8c03-69b31f60de07" />
<img width="586" height="69" alt="imagen" src="https://github.com/user-attachments/assets/f0962c96-5b18-446b-b2d0-ee8abdc3101b" />
<img width="586" height="69" alt="imagen" src="https://github.com/user-attachments/assets/fff0da8a-7bbc-4d46-9adf-68ac58127fba" />

- Cuando lo tengamos configurado, conectamos un cliente a la red del servidor y ponemos "https://(IP)/phpldapadmin"  en el buscador.

<img width="906" height="468" alt="imagen" src="https://github.com/user-attachments/assets/c83e0326-6963-4259-a9b8-3142c4fcf881" />

- Podemos crear un usuario facilmente desde la pagina

<img width="646" height="637" alt="imagen" src="https://github.com/user-attachments/assets/066c0bfa-5aea-41d6-a42f-9b36908020f5" />

- Y se nos añadiria dentro de la lista de usuarios

<img width="328" height="276" alt="imagen" src="https://github.com/user-attachments/assets/b67da126-fbfb-4994-98db-b3713d0aa9b0" />

## INSTALACION Y CONFIGURACION DE LOS USUARIOS
- Entramos a nuestro cliente de Ubuntu y instalamos lo siguiente con este comando:"sudo apt install libpam-ldap libnss-ldap nss-updatedb libnss-db nscd ldap-utils"

- Se nos abra una pantalla en donde hay que poner la IP.

<img width="708" height="317" alt="imagen" src="https://github.com/user-attachments/assets/6ed6ea4c-983a-47c0-8b57-acbd302919fe" />

- Despues ponemos el DN.

<img width="708" height="317" alt="imagen" src="https://github.com/user-attachments/assets/a63d661c-980f-4438-8168-9d05527b7823" />

- Aplicamos la version de LDAP que queremos.

<img width="708" height="317" alt="imagen" src="https://github.com/user-attachments/assets/fb5b0bb2-5d45-4f2a-8da8-99fd0532808e" />

- Le damos que si al comportamiento de contraseñas.

<img width="708" height="317" alt="imagen" src="https://github.com/user-attachments/assets/9ad9d180-778e-4e41-99db-05b22aa25931" />

- Ponemos el usuario.

<img width="686" height="317" alt="imagen" src="https://github.com/user-attachments/assets/140ecc7d-1b66-4aea-8c36-17be3dc625cc" />

- Añadimos la contraseña del LDAP root.

<img width="718" height="392" alt="imagen" src="https://github.com/user-attachments/assets/b464bac1-69d4-4df9-b875-ff0ee3998867" />

- Modificamos el "/etc/nsswitch.conf".

<img width="718" height="392" alt="imagen" src="https://github.com/user-attachments/assets/83f69daa-51b9-48ba-903d-fb4082eb51b2" />

- Y una vez todo configurado, ponemos este comando para actualizar el NSS.

<img width="437" height="53" alt="imagen" src="https://github.com/user-attachments/assets/3694e0ba-f984-4d86-a0fd-0bada3bb7ba6" />

- Comprobamos el fichero "ldap.conf"

<img width="558" height="280" alt="imagen" src="https://github.com/user-attachments/assets/4d12ed8f-e3d5-4051-8b0b-fc7900019ced" />

- Con el comando "getent passwd" podemos ver los usuarios.

<img width="717" height="280" alt="imagen" src="https://github.com/user-attachments/assets/73978d12-7093-42f1-a279-a155a514d7ed" />

- Activamos la autentificacion PAM con el comando "sudo pam-auth-update" y le damos a lo siguiente antes de darle a Aceptar.

<img width="717" height="396" alt="imagen" src="https://github.com/user-attachments/assets/a7915a19-55ee-466b-8c68-37dc9138720a" />

- Y una vez hecho, ya estara configurado en el PAM.

<img width="717" height="396" alt="imagen" src="https://github.com/user-attachments/assets/fa76ae27-e668-4b5f-ac27-61dbe46856c0" />

- Una vez que reiniciemos la maquina, deberian salir.
