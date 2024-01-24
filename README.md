# ¿Qué es Efactura Printer?

**Efactura Printer** es un servicio Windows que permite imprimir automáticamente facturas electrónicas creadas desde servicios externos después de ser autorizadas.

**Efactura Printer** se conecta al servicio de integraciones y está preparado para recibir la información de las facturas creadas por el contribuyente y dependiendo de qué puntos de facturación y sucursales deba recibir imprimirá automáticamente las facturas creadas.

Para utilizar **Efactura Printer** debe contar con una cuenta de Efacturapty, la cual puede crear en [admin.efacturapty.com](admin.efacturapty.com) y configurarla en la pestaña de personalización para activar la impresión automática.

# Instalación y configuración

Descargue el zip de Efactura Printer Release v1.0.0 y descomprima en una carpeta local.

Descargue el programa [PDFtoPrinter for Windows](https://mendelson.org/pdftoprinter.html).

Edite el archivo **appsetting.json** para configurar los siguientes valores:

- **PrinterPdfAppPath**: Ruta y nombre del archivo de impresión de pdf (PDFtoPrinter) que se descargó. Por ejemplo: I:\\printtopdf\\PDFtoPrinter.exe

- **PrinterName**: Nombre de la impresora que se usará.

- **APIKey**: API Key generado en el sitio admin.efacturapty.com

- **CafeDownloadPath**: Carpeta que debe crear manualmente en la que se guardan las facturas descargadas para su impresión.

- **RucEmitter**: RUC del contribuyente emisor de la factura.

- **CafeTemplate**: tipo de impresión que puede ser: **carta** o **termica**

- **Facturacion**: Lista de sucursales y puntos de facturación que se imprimirán desde esta impresora, Tiene el formato de lista:

      [{
  
        "CodigoSucursal": "0000","PuntosFacturacion": ["100","102"]
  
      },
  
      {
  
        "CodigoSucursal": "0002","PuntosFacturacion": ["200","202"]
  
      }]`

Kestrel/Endpoints/Http/Url: Permite establecer el puerto local que utilizará el servicio para recibir las peticiones.

# Creación del servicio

Desde línea de comando, con privilegio de Administrador ejecutar:

`sc.exe create "efacturaPrinter " binpath=ubicacion\_ efacturaPrinter \_exe`

Desde la consola de Servicios de Windows, se debe configurar el servicio **Efactura Printer** para que lo use la cuenta del usuario con la que se hará uso del servicio. Debe ingresarse la contraseña de la cuenta o del correo asociado a la cuenta.

![ServiceLogOn](https://github.com/efacturapty/efactura-printsvc/assets/146016561/11fd58f4-f899-4e21-a210-067b3a3ee541)

Igualmente, desde la consola de Servicios de Windows, puede configurar el servicio Efactura Printer para que inicie en forma automática, cada que inicie Windows.

![ServiceStartUp](https://github.com/efacturapty/efactura-printsvc/assets/146016561/0873d105-9c76-4a87-bb5b-d51e83c965f3)
