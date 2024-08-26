# ¿Qué es Efactura Printer?

**Efactura Printer** es un servicio Windows que permite imprimir automáticamente facturas electrónicas creadas desde servicios externos después de ser autorizadas.

**Efactura Printer** se conecta al servicio de integraciones y está preparado para recibir la información de las facturas creadas por el contribuyente y dependiendo de qué puntos de facturación y sucursales deba recibir imprimirá automáticamente las facturas creadas.

Para utilizar **Efactura Printer** debe contar con una cuenta de Efacturapty, la cual puede crear en [admin.efacturapty.com](admin.efacturapty.com) y configurarla en la pestaña de personalización para activar la impresión automática.

# Instalación y configuración

**Requisitos Previos:**
1. Contar con una impresora configurada en su sistema.
2. Descargar el archivo ZIP que contiene todos los ejecutables necesarios para la instalación de Efactura Printer.

**Paso 1: Descarga y Extracción de Archivos**
1. **Descarga**: Descargar el archivo ZIP de **Efactura Printer Release v1.0.0** desde el sitio oficial.
2. **Extracción**: Descomprimir el archivo ZIP en una carpeta local de tu elección.

**Paso 2: Configuración de la Aplicación**
1. **Edición del archivo** '**appsetting.json**': Dentro de la carpeta descomprimida, localiza y edita el archivo '**appsetting.json**' para configurar los siguientes valores:
   
   - '**APIKey**': Inserta el API Key generado en admin.efacturapty.com.
   - '**RucEmitter**': Ingresa el RUC del contribuyente emisor.
   - '**Facturacion**': Configura la lista de sucursales y puntos de facturación que esta impresora gestionará.
     
     [{
  
        "CodigoSucursal": "0000","PuntosFacturacion": ["100","102"]
  
      },
  
      {
  
        "CodigoSucursal": "0002","PuntosFacturacion": ["200","202"]
  
      }]`
   

**Paso 3: Configuración para Ejecución Automática al Iniciar Windows**

1. **Crear Acceso Directo**:
   
   - Abre la carpeta donde se extrajo Efactura Printer.
   - Haz clic derecho en el archivo ejecutable ('**EfacturaPrinter.exe**') y selecciona **Crear acceso directo**.

2. **Mover Acceso Directo a la Carpeta de Inicio**:

   - Presiona la tecla del logotipo de Windows + R.
   - En el cuadro de diálogo de ejecución, escribe '**shell:startup**' y presiona '**Aceptar**'. Se abrirá la carpeta "Inicio" de Windows.
   - Copia el acceso directo creado en el paso anterior y pégalo en esta carpeta.

**Paso 4: Prueba de Funcionamiento**

1. Reinicia tu computadora.
2. Verifica que Efactura Printer se ejecute automáticamente al iniciar Windows.
3. Comprueba que la aplicación funcione correctamente enviando una factura de prueba desde tu sistema Efacturapty y asegurándote de que se imprima automáticamente.

Siguiendo estos pasos, habrá instalado y configurado correctamente Efactura Printer para su ejecución automática al iniciar Windows.


