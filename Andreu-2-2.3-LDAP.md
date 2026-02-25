# SERVICIO LDAP
Seguiremos estos pasos para instalar OpenLDAP en un servidor Linux:
- Instalamos un servidor Linux dentro de nuestra maquinas y ponemos el siguiente comando para instalarlo:

<img width="546" height="136" alt="image" src="https://github.com/user-attachments/assets/d087630e-6434-4a17-9ba3-1cd89fbed802" />


- Se nos abrira un menu para poner la contraseña y lo ponemos para que terminar la instalacion.

  <img width="718" height="207" alt="image" src="https://github.com/user-attachments/assets/6456ac02-dea2-465d-a78f-cebd2c6d5f71" />

- Tambien editamos el directorio Netplan y lo configuramos de la siguiente manera:

<img width="722" height="296" alt="image" src="https://github.com/user-attachments/assets/ed737659-dd28-4d46-8259-41c7657d5296" />

- Miramos con el comando "dpkg –L slapd | grep (cualquier archivo)" para mirar dentro del archivo que nos ha creado la instalacion por el nombre que le pongamos, destacandolos con color por el -L.

<img width="541" height="294" alt="image" src="https://github.com/user-attachments/assets/6fcd226f-31cf-4868-89c4-265e998310e5" />
<img width="600" height="782" alt="imagen" src="https://github.com/user-attachments/assets/419b3831-b297-4d0a-bf90-204053848d2e" />
<img width="428" height="167" alt="image" src="https://github.com/user-attachments/assets/f42911fe-0f95-40ec-b8eb-f08caae5c1e9" />
<img width="602" height="785" alt="imagen" src="https://github.com/user-attachments/assets/d31c9f94-f219-42dc-b612-fbf5fbe902b8" />

- Con sudo dpkg-reconfigure slapd iniciamos la configuración del servicio
<img width="954" height="280" alt="imagen" src="https://github.com/user-attachments/assets/61c7537f-23cc-4649-acbf-6040d43703b6" />

-Le ponemos un nombre de organizacion.

<img width="721" height="183" alt="image" src="https://github.com/user-attachments/assets/f0dcae63-aadf-485d-ac99-346ca14b2f18" />

- Una vez puesta la contraseña, en este menu ponemos no.

<img width="638" height="203" alt="imagen" src="https://github.com/user-attachments/assets/593a63fb-d743-491d-a27f-8fff880753ec" />

- Y aqui le damos que si para que cree una nueva base de datos.
- Y movemos la base antigua por si acaso.

<img width="940" height="203" alt="imagen" src="https://github.com/user-attachments/assets/20b31d29-d08e-40f4-8fd9-ed202e4651f7" />

- Una vez ya esto, con el servidor podemos poner estos comandos:

<img width="1014" height="263" alt="imagen" src="https://github.com/user-attachments/assets/44e7163a-59cc-4aa5-8555-a51928b03f65" />

- Creamos un grupo de configuracion llamado "group.ldif" y ponemos lo siguiente:
- <img width="552" height="45" alt="image" src="https://github.com/user-attachments/assets/540526b7-63ba-4f8f-8359-8a611e89e589" />
<img width="494" height="155" alt="image" src="https://github.com/user-attachments/assets/2729ecbc-96c0-47ed-9ae3-3dfa469b8ace" />


- Y añadimos el usuario que queriamos a este
- Creamos otro .ldif para los usuarios

<img width="490" height="284" alt="image" src="https://github.com/user-attachments/assets/0665ffc3-a508-423e-a2b4-8bbef09fbd05" />

- Y añadimos el usuario a este tambien

<img width="722" height="29" alt="image" src="https://github.com/user-attachments/assets/490a77c8-df05-4772-808a-03ad964e3e29" />

- En el archivo "usuarios.ldif" hay que poner tambien esto para que tenga una contraseña.

<img width="191" height="18" alt="imagen" src="https://github.com/user-attachments/assets/a5fd7a24-1686-4f4d-99e7-fb377e453f5c" />

- Con el comando "ldapsearch" podemos ver el arbol en que estan los usuarios que hemos creado
<img width="596" height="299" alt="image" src="https://github.com/user-attachments/assets/d01eab52-156a-4202-8d54-af5fac93b68b" />

No me deja hacerlo otra vez.
## INSTALACION DE PHPLDAPADMIN (TAMBIEN EN FORMA GRAFICA)
- Usamos este comando para instalarlo:

<img width="514" height="120" alt="image" src="https://github.com/user-attachments/assets/59593fae-63d8-4a02-8023-d1f6deb8ed38" />

- Una vez instalado, entramos dentro de "/usr/share/phpldapadmin/config/config.php" y editamos lo siguiente:

<img width="586" height="69" alt="imagen" src="https://github.com/user-attachments/assets/6bda1793-fba2-4ed3-8c03-69b31f60de07" />
<img width="586" height="69" alt="imagen" src="https://github.com/user-attachments/assets/f0962c96-5b18-446b-b2d0-ee8abdc3101b" />
<img width="586" height="69" alt="imagen" src="https://github.com/user-attachments/assets/fff0da8a-7bbc-4d46-9adf-68ac58127fba" />

- Cuando lo tengamos configurado, conectamos un cliente a la red del servidor y ponemos "https://(IP)/phpldapadmin"  en el buscador.

<img width="906" height="468" alt="imagen" src="https://github.com/user-attachments/assets/c83e0326-6963-4259-a9b8-3142c4fcf881" />

- Podemos crear un usuario facilmente desde la pagina


- Y se nos añadiria dentro de la lista de usuarios


## INSTALACION Y CONFIGURACION DE LOS USUARIOS
- Entramos a nuestro cliente de Ubuntu y instalamos lo siguiente con este comando: sudo apt install libpam-ldap libnss-ldap nss-updatedb libnss-db nscd ldap-utils
<img width="803" height="215" alt="image" src="https://github.com/user-attachments/assets/6214a22f-4b0f-4200-8ca3-aa0a660f1158" />

- Se nos abra una pantalla en donde hay que poner la IP.

<img width="775" height="455" alt="image" src="https://github.com/user-attachments/assets/ba404f62-df93-4f0a-b093-d8534cb5214b" />

- Despues ponemos el DN.

<img width="708" height="317" alt="imagen" src="https://github.com/user-attachments/assets/a63d661c-980f-4438-8168-9d05527b7823" />

- Aplicamos la version de LDAP que queremos. En mi caso, al version 3.

<img width="708" height="317" alt="imagen" src="https://github.com/user-attachments/assets/fb5b0bb2-5d45-4f2a-8da8-99fd0532808e" />

- Le damos que si al comportamiento de contraseñas.

<img width="708" height="317" alt="imagen" src="https://github.com/user-attachments/assets/9ad9d180-778e-4e41-99db-05b22aa25931" />

- Ponemos el usuario.

<img width="686" height="317" alt="imagen" src="https://github.com/user-attachments/assets/140ecc7d-1b66-4aea-8c36-17be3dc625cc" />

- Añadimos la contraseña del LDAP root.(servidor)

<img width="718" height="392" alt="imagen" src="https://github.com/user-attachments/assets/b464bac1-69d4-4df9-b875-ff0ee3998867" />

- Modificamos el "/etc/nsswitch.conf".

<img width="856" height="603" alt="image" src="https://github.com/user-attachments/assets/526eb4c5-0bcf-4480-abea-69d40000fa24" />

- Y una vez todo configurado, ponemos este comando para actualizar el NSS.

<img width="203" height="19" alt="image" src="https://github.com/user-attachments/assets/6d59377c-5e4d-44ac-b79f-bc8038099f7e" />

- Comprobamos el fichero "ldap.conf"

<img width="558" height="280" alt="imagen" src="https://github.com/user-attachments/assets/4d12ed8f-e3d5-4051-8b0b-fc7900019ced" />

- Con el comando "getent passwd" podemos ver los usuarios.

<img width="717" height="280" alt="imagen" src="https://github.com/user-attachments/assets/73978d12-7093-42f1-a279-a155a514d7ed" />

- Activamos la autentificacion PAM con el comando "sudo pam-auth-update" y le damos a lo siguiente antes de darle a Aceptar.

<img width="717" height="396" alt="imagen" src="https://github.com/user-attachments/assets/a7915a19-55ee-466b-8c68-37dc9138720a" />

- Y una vez hecho, ya estara configurado en el PAM.

<img width="717" height="396" alt="imagen" src="https://github.com/user-attachments/assets/fa76ae27-e668-4b5f-ac27-61dbe46856c0" />

- Una vez que reiniciemos la maquina, deberian salir.
