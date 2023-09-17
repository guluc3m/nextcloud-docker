# gul-nextcloud

## Instalación
Para levantar el Nextcloud del GUL es necesario seguir los siguientes pasos (siempre y cuando hayas montado el NFS de la Universidad, por defecto en `/mnt/repositorios`, puedes comprobar la configuración del NFS en el archivo `/etc/fstab` del servidor):

1. Copia los archivos `.sample` a archivos sin el `.sample`.
   E.g.: `db.env.sample` → `db.env`.
1. EN CASO DE QUE NO EXISTAN, crear las carpetas `/mnt/repositorios/nextcloud`, `/mnt/repositorios/nextcloud/db` y `/mnt/repositorios/nextcloud/data` en ellas se almacenaran BBDD y datos respectivamente, si existen prviamente ignora este paso para preservar los datos. Si ya no usamos el NFS o ha cambiado la ruta, acuerdate de cambiarla en el `docker-compose.yml`.
3. Cambia las credenciales en `db.env`.
4. Ejecutar `docker compose up -d`
5. Añade la configuración proporcionada `cloud.conf` el proxy inverso NGINX.
6. Listo, sigue los pasos de condifuración de la web.

**IMPORTANTE:** el dominio de este servicio NO debe estar en el archivo `/etc/hosts` para que el collabora CODE funcione.

## Actualización
Para actualizar basta con realizar un `docker compose pull` y `docker compose up -d`.

