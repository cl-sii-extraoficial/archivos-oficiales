# SII "factura_electronica" / XML schemas

> This file was originally posted at [fyntex/lib-cl-sii-python@7030d96](https://github.com/fyntex/lib-cl-sii-python/pull/6/commits/7030d96b1a2dccf667dee6135a97c3cee9ff6d6e) by [@glarrain](https://github.com/glarrain)

This directory contains all the files of `schema_dte.zip`, plus this text file.
All the files have been preserved as they were; schemas are in their original text encoding
(ISO-8859-1) and have not been modified in the slightest way.

The most significant structures are:
- XML element `EnvioDTE`: "Envio de Documentos Tributarios Electronicos".
- XML data type `DTEDefType`: "Documento Tributario Electronico".

Note: DTE means "Documento Tributario Electrónico".


## Source


### Original & Official

[schema_dte.zip](http://www.sii.cl/factura_electronica/schema_dte.zip) (2021-03-12),
referenced from official webpage
[SII](http://www.sii.cl)
/ [Factura electrónica](http://www.sii.cl/servicios_online/1039-.html)
/ [FORMATO XML DE DOCUMENTOS ELECTRÓNICOS](http://www.sii.cl/factura_electronica/formato_xml.htm)
as
"[Bajar schema XML de Documentos Tributarios Electrónicos](http://www.sii.cl/factura_electronica/schema_dte.zip) (Incluye Documentos de exportación)"


### Updates

Unfortunately the files available on SII's website are outdated with respect to the regulations
(and even with respect to the documentation PDFs published alongside).

Schema files will be updated as necessary, indicating the source in the corresponding commit.

- 2021-03-12
  - Files:
    - `DTE_v10.xsd`
    - `SiiTypes_v10.xsd`
  - Source: [schema_cesion_201912.zip](https://www.sii.cl/factura_electronica/schema_cesion_201912.zip)
  - MD5: `33639f61ef3aa0ec785557b1c8778cea`

## Contents


### Detail

- `DTE_v10.xsd`: "XSD principal y que incluye a los 3" otros XSD.
  - MD5: `ab4aae9dd23588f260d37a846e70439a`.
  - SHA256: `1ba39d9bdaf96955cf6f3c36a7ce004cc6df18c4dd759705af44dc56f94b2d28`
  - XML target namespace: `http://www.sii.cl/SiiDte`.
  - XML included/imported schemas: `SiiTypes_v10.xsd`, `xmldsignature_v10.xsd`.
  - XML elements:
    - `DTE`: (no description nor annotations)
  - XML data types:
    - `DTEDefType`: "Documento Tributario Electronico".

- `EnvioDTE_v10.xsd`: "descripción de documentos"
  - MD5: `6ed5ceeb7508df3c9d6e99f955751a94`.
  - SHA256: `e86aae6ab21cbce8e93ddcf2df4f8b80cac42bab3c8da845d0756917e866aa2a`
  - XML target namespace: `http://www.sii.cl/SiiDte`.
  - XML included/imported schemas: `DTE_v10.xsd`, `xmldsignature_v10.xsd`.
  - XML elements:
    - `EnvioDTE`: "Envio de Documentos Tributarios Electronicos".
  - XML data types: none.

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

- Enums `DOCType`, `DocType`, `DTEType` and `DTEFacturasType` (all of them in `SiiTypes_v10.xsd`)
  are **very** similar.
- Enums `DocType` and `DTEType` have exactly the same elements (although descriptions differ).
- The elements of the following enums are strictly subgroups of enum `DOCType`:
  - `DocType` and `DTEType`: same elements.
  - `DTEFacturasType`
  - `LIQType`: "Tipos de Liquidaciones".
  - `EXPType`: "Tipos de Facturas de  Exportacion".
