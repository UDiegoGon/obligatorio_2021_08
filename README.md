# obligatorio_2021_08

-----MODIFICACIONES-----

-  Todas las instalaciones de paquetes han sido habilitadas    para sistemas operativos dentro de las distribuciones RedHat y Debian usando "dnf" y "apt" respectivamente.

- El archivo de inventario "host.ini" fue modificado para alojar dos nuevos servidores uno entrando en el grupo "webservers" y otro en "dbservers"

- Se agrego archivo "ansible.cfg", el cual contiene la configuracion de ansible en este repositorio. En el mismo se especificó la ruta del inventario y el usuario remoto para la conexion SSH.  

- Todos los errores de sintaxis en los playbooks se han modificado y anidado correctamente.

- Se ha habilitado la accion de volverse root en "site.yml" para correr las acciones en modo privilegiado.

- Se ha modificado la instalacion de NTP para los servidores RedHat cambiandolo a su contraparte Chrony. En base a esto se agrego un archivo Jinja en los templates en el rol "common" que contiene la configuracion de este.

- Se ha instalado EPEL en los servidores de base de datos para poder permitir los paquetes del playbook.

- Se creó una tarea en "headlers" para reiniciar el servicio Chrony

- Se especificaron los permisos de los archivos usando el modulo "mode".

- En "deb>tasks>main.yml" en la linea 46 se cambio el valor "iptouch" por "touch".

- En el playbook principal del rol "web" se habilito la instalacion de apache2 para los servidores Debian.

- El uso de las variables en el codigo fue arreglado y ahora las variables llevan comillas, ejemplo: "{{ item }}" en vez de {{ item }}.



-----USO EMPLEADO-----

- Se va a utilizar este rol para las funciones de base de datos y de servicios web en ambos servidores de nuestra instalacion, uno siendo un servidor CentOS 8 el cual sera utilizado como servidor de base de datos y un servidor Ubuntu en cual utilizara las funciones de WebServer.
