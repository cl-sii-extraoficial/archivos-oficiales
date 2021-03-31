# SII "Registro de Transferencia de Crédito (RTC)" / XML schemas

> This file was originally posted at [fyntex/lib-cl-sii-python@c7adc5a](https://github.com/fyntex/lib-cl-sii-python/pull/18/commits/c7adc5a2cbf9049c6143661547c8e19aa436e220)
> by [@glarrain](https://github.com/glarrain)

This directory contains all the files of [`2019-12-12-schema_cesion.zip`](../README.md), plus this text file.
All the files have been preserved as they were; schemas are in their original text encoding
(ISO-8859-1) and have not been modified in the slightest way.

Note:
- AEC means "Archivo Electrónico de Cesión".
- RTC: "Registro Transferencia de Crédito" aka RPETC; "Registro Electrónico de Cesión de Créditos".
- RPETC: "Registro Público Electrónico de Transferencia de Crédito" aka RTC.


## Source


### Original & Official

[`schema_cesion_201912.zip`](../README.md) (2019-12-12)


## Contents


### Detail

- `AEC_v10.xsd`: main schema; it includes (directly or indirectly) all the others of this section.
  - MD5: `8e80522d91bcf99077c12e15354eeae4`.
  - SHA256: `809890d58376ef74bbd4162883df6e89d09231e783e0368486d497fce7308666`
  - XML target namespace: `http://www.sii.cl/SiiDte`.
  - XML included/imported schemas: `Cesion_v10.xsd`, `DTECedido_v10.xsd`, `xmldsignature_v10.xsd`.
  - XML elements:
    - `AEC`: "Archivo Electronico de Cesion"
      - `DocumentoAEC`: "Documento de AEC"
        - `Caratula`: "Informacion de AEC"
        - `Cesiones`: "Cesiones"
          - ref `DTECedido`: "Representacion XML y Grafica del DTE Cedido"
          - ref `Cesion` (1..N occurrences):
            "Informacion Electronica de Recepcion y Aceptacion del DTE por Parte del Receptor"
  - XML data types: no explicit definitions.

- `Cesion_v10.xsd`: ?
  - MD5: `8db534d686bc84fc7960199dd5fdacd8`.
  - SHA256: `ebd5bb1c7a6e6b349b559146f696e082301094021a921947766c5ca863e98e16`
  - XML target namespace: `http://www.sii.cl/SiiDte`.
  - XML included/imported schemas: `SiiTypes_v10.xsd`, `xmldsignature_v10.xsd`.
  - XML elements:
    - `Cesion`: "Envio de Informacion de Transferencias  Electronicas".
  - XML data types:
    - `CesionDefType`: "Documento Tributario Electronico" (sic).
      Relevant elements:
      - `DocumentoCesion`: (no description nor annotations)
        - `SeqCesion`: "Secuencia de Cesiones (1, 2, 3, ... )".
        - `IdDTE`: "Identificacion del DTE Cedido".
        - `Cedente`: "Identificacion del Cedente".
        - `Cesionario`: "Identificacion del Cesionario".
        - `MontoCesion`: "Monto del Credito Cedido".
        - `UltimoVencimiento`: "Fecha de Ultimo Vencimiento".
        - `OtrasCondiciones`: "Otras Condiciones de la Cesion".
        - `eMailDeudor`: "Correo Electronico del Deudor del DTE".
        - `TmstCesion`: "TimeStamp de la Cesion del DTE".

- `DTECedido_v10.xsd`: ?
  - MD5: `b2fd1907af733ae9401604c694837a85`.
  - SHA256: `8cf524ec13ac2c48d99aed73ccd25c0a6a8c74dd81925f35b416c78ce22f0618`
  - XML target namespace: `http://www.sii.cl/SiiDte`.
  - XML included/imported schemas: `DTE_v10.xsd`, `Recibos_v10.xsd`, `xmldsignature_v10.xsd`.
  - XML elements:
    - `DTECedido`: "DTE con Imagen y Recibos".
  - XML data types:
    - `DTECedidoDefType`: "Documento Tributario Electronico".
      Relevant elements:
      - `DocumentoDTECedido`: (no description nor annotations)
        - ref `DTE`: "Representacion XML del DTE Cedido".
        - `ImagenDTE` (optional): "Representacion PDF del DTE Cedido" (binary as base64)
        - ref `Recibo` (0..N occurrences):
          "Informacion Electronica de Recepcion y Aceptacion del DTE por Parte del Receptor".
        - `ImagenAR` (optional):
          "Representacion PDF del los Acuse de Recibo" (sic) (binary as base64)
        - `TmstFirma`:
          "Fecha y Hora en que se Firmo Digitalmente el Documento Cedido AAAA-MM-DDTHH:MI:SS".

- `DTE_v10.xsd`: ?
  - MD5: `ab4aae9dd23588f260d37a846e70439a`.
  - SHA256: `1ba39d9bdaf96955cf6f3c36a7ce004cc6df18c4dd759705af44dc56f94b2d28`
  - XML target namespace: `http://www.sii.cl/SiiDte`.
  - XML included/imported schemas: `SiiTypes_v10.xsd`, `xmldsignature_v10.xsd`.
  - XML elements:
    - `DTE`: (no description nor annotations)
  - XML data types:
    - `DTEDefType`: "Documento Tributario Electronico".

- `Recibos_v10.xsd`: ?
  - MD5: `620cf4867d8ba9c16dba74ab05830963`.
  - SHA256: `20eaf6f76fa966b90bf2a7bd17f8b373a7fcb6c60f97aae11377cb2999c57605`
  - XML target namespace: `http://www.sii.cl/SiiDte`.
  - XML included/imported schemas: `SiiTypes_v10.xsd`, `xmldsignature_v10.xsd`.
  - XML elements:
    - `Recibo`:
        doc 1: "Comprobante de Recepcion de Mercaderias o Servicios Prestados".
        doc 2: "Recibos de Recepcion de Mercaderias o Servicios Prestados".
  - XML data types:
    - `ReciboDefType`: "Documento Tributario Electronico" (sic)
      Relevant elements:
      - `DocumentoRecibo`: "Identificacion del Documento Recibido" (sic)
        - `TipoDoc`: "Tipo de Documento".
        - `Folio`: "Folio del Documento".
        - `FchEmis`: "Fecha Emision Contable del Documento (AAAA-MM-DD)".
        - `RUTEmisor`: "RUT Emisor del Documento".
        - `RUTRecep`: "RUT Receptor del Documento".
        - `MntTotal`: "Monto Total del Documento".
        - `Recinto`: "Lugar donde se materializa la recepción conforme".
        - `RutFirma`: "RUT de quien Firma el Recibo".
        - `Declaracion` (fixed string):
          "Texto Ley 19.983, acredita la recepcion mercaderías o servicio.".
        - `TmstFirmaRecibo`: "Fecha y Hora de la Firma del Recibo".

- `SiiTypes_v10.xsd`: "descripción de tipos de datos"
  - MD5: `5985df947f8b4d4c9daffcf50ca74b3a`.
  - SHA256: `5002fef1cd9592de1191359f1995592d48d18f2274c5659bf2e47129807f434d`
  - XML target namespace: `http://www.sii.cl/SiiDte`.
  - XML included/imported schemas: none.
  - XML elements: none.
  - XML data types:
    - `DOCType`: "Todos los tipos de Documentos Tributarios Electronicos".
    - `DocType`: "Tipos de Documento".
    - `DTEType`: "Tipos de Documentos Tributarios Electronicos".
    - `DTEFacturasType`: "Tipos de Documentos Tributarios Electronicos" (same description as
      `DTEType` but different elements).
    - `LIQType`: "Tipos de Liquidaciones".
    - `EXPType`: "Tipos de Facturas de  Exportacion".
    - `RUTType`: "Rol Unico Tributario (99..99-X)".
    - `MedioPagoType`: "Medios de Pago".
    - `TipMonType`: "Tipos de Moneda de Aduana".
    - `MontoType`: "Monto de 18 digitos".
    - `MntImpType`: "Monto de Impuesto - 18 digitos".
    - `ValorType`: "Monto de 18 digitos - Positivo o Negativo".
    - `FolioType`: "Folio de DTE - 10 digitos".
    - `FolioRType`: "Folio de Referencia - 18 digitos (incluye el cero)".
    - `ImpAdicType`: "Tipo de Impuesto o Retencion Adicional".
    - `ImpAdicDTEType`: "Tipo de Impuesto o Retencion Adicional de los DTE".
    - `MailType`: "Dirección email".
    - `DineroPorcentajeType`: "Unidad en que se expresa el Valor".
    - `NroResolType`: "Número de Resolución".
    - `RznSocLargaType`: "Razón Social (max 100)".
    - `RznSocCortaType`: "Razón Social (max 40)".
    - `DireccSoloDTEType`: "Dirección (maz 60)" (sic).
    - `DireccType`: "Dirección (max 80)".
    - `ComunaType`: "Comuna".
    - `CiudadType`: "Ciudad".
    - `FonoType`: "Fono".
    - `NombreType`: "Nombre".
    - `FechaType`: "Fecha entre 2000-01-01 y 2050-12-31".
    - `FechaHoraType`: "FechaType + hora entre 00:00 y 23:59;".
    - `TipoTransCOMPRA`: "Tipo de Transacción para el comprador".
    - `TipoTransVENTA`: "Tipo de Transacción para el vendedor".
    - `Dec16_2Type`: "Monto con 16 Digitos de Cuerpo y 2 Decimales".
    - `Dec14_4Type`: "Monto con 14 Digitos de Cuerpo y 4 Decimales".
    - `Dec14_4-0Type`: "Monto con 14 Digitos de Cuerpo y 4 Decimales partiendo de cero".
    - `Dec8_4Type`: "Monto con 8 Digitos de Cuerpo y 4 Decimales".
    - `Dec6_4Type`: "Monto con 6 Digitos de Cuerpo y 4 Decimales".
    - `Dec12_6Type`: "Monto con 12 Digitos de Cuerpo y 6 Decimales".
    - `PctType`: "Monto de Porcentaje ( 3 y 2)".

- `xmldsignature_v10.xsd`: "descripción de la firma electrónica"
  - MD5: `8b83aaae477a57d829b075230237102c`.
  - SHA256: `427e3225cd379ae92bae464b892dbf964665af92d453ac61774cffab38b95edb`
  - XML target namespace: `http://www.w3.org/2000/09/xmldsig#`.
  - XML included/imported schemas: none.
  - XML elements:
    - `Signature`: "Firma Digital sobre Documento".
  - XML data types:
    - `SignatureType`: "Firma Digital con Restricciones".


### Notes

- File `xmldsignature_v10.xsd` is identical to [`xmldsignature_v10.xsd`](../../../dte/2011-05-30-schema_dte/schema_dte/xmldsignature_v10.xsd) in the [DTE XML schema directory](../../../dte/2011-05-30-schema_dte/schema_dte).
