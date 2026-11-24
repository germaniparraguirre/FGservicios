FG SERVICIOS E INSTALACIONES - SISTEMA DE PRESUPUESTOS (V1)
===========================================================

REQUISITOS
- Hosting web con cPanel.
- PHP 8.1 o superior (recomendado 8.2+).
- Extensiones PHP: PDO, PDO_MySQL, mbstring.
- MySQL 5.7+ o MariaDB 10.4+.
- Certificado SSL activo (HTTPS).

INSTALACIÓN
1. En cPanel, crear una base de datos MySQL, un usuario y asignarlo a la base
   con todos los permisos. Guardar host, nombre, usuario y contraseña.
2. Desde phpMyAdmin, seleccionar la base recién creada e importar schema.sql.
3. Copiar todos los archivos y la carpeta assets al directorio del dominio
   (por ejemplo public_html o public_html/presupuestos).
4. Renombrar config.example.php a config.php y completar los datos MySQL.
5. Abrir el dominio desde el navegador. La primera pantalla permite crear
   el usuario administrador. Usar una contraseña única de al menos 10 caracteres.
6. Ingresar y desde Empresa completar CUIT, teléfono, correo, dirección y
   prefijo de numeración.
7. Desde Usuarios, crear las cuentas para los empleados.

USO
- Clientes: registrar clientes.
- Servicios y materiales: cargar catálogo y precios en ARS y USD.
- Nuevo presupuesto: elegir cliente, moneda, fechas y renglones.
- Ver / PDF: abrir el presupuesto y usar "Imprimir / Guardar PDF".
  En el diálogo de impresión del navegador seleccionar "Guardar como PDF".
- Empresa: configurar los datos que aparecerán en los documentos.

SEGURIDAD Y OPERACIÓN
- Activar HTTPS antes de usar el sistema con información real.
- No compartir la cuenta administradora; crear usuarios individuales.
- Realizar copias de seguridad periódicas de la base MySQL y de los archivos.
- Borrar config.example.php del servidor una vez instalado.
- No subir schema.sql/config.php a repositorios públicos.
- Esta V1 implementa roles admin/empleado; solo admin administra usuarios
  y datos de empresa. Los empleados pueden operar presupuestos, clientes y catálogo.
- No incluye todavía recuperación de contraseña, carga de imagen de logo,
  edición/borrado de presupuestos ni envío automático por WhatsApp.
- El PDF se genera mediante la función de impresión del navegador; no requiere
  instalar bibliotecas externas en el hosting. La plantilla es imprimible y
  se puede personalizar en assets/style.css e index.php.

IMPORTANTE
Este paquete es una primera versión funcional para pruebas. Antes de usarlo
en producción con datos sensibles, conviene probarlo en un subdominio,
verificar las copias de seguridad y solicitar una revisión de seguridad
al administrador del hosting o desarrollador responsable.
