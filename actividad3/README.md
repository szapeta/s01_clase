# Origen del problema

El problema se origina debido a que en el directorio, de publicación del sitio de react, solo se encuentra un archivo index.html y no encuentra ningun otro archivo.

# Solucion

SE debe configurar que al no encontrar un archivo, se debe realizar la busqueda en uno archivo predeterminado y luego buscar en el Router que se configuro previamente en React

# Detalle

Se crea un archivo de configuracion de nginx.conf

Se copia este archivo de configuracion hacia el directorio de nginx para que sepa que debe hacer la busqueda.

En el docker file, se agrega una linea para copiar el archivo nginx.conf hacia el directorio de nginx