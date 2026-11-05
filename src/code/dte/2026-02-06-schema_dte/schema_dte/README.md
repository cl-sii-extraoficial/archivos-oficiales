# SII "Documento Tributario Electrónico (DTE)" / XML schemas

> This file is based on the one of [version 2011-05-30](../../2011-05-30-schema_dte/schema_dte/README.md).

This directory contains all the files of [2026-02-06-schema_dte.zip](../README.md), plus this text file.
All the files have been preserved as they were; schemas are in their original text encoding
(ISO-8859-1) and line endings, and have not been modified in the slightest way.

The most significant structures are:
- XML element `EnvioDTE`: "Envio de Documentos Tributarios Electronicos".
- XML data type `DTEDefType`: "Documento Tributario Electronico".

Note: DTE means "Documento Tributario Electrónico".


## Source


### Original & Official

[schema_dte.zip](../README.md) (2026-02-06),
referenced from official webpage
[SII](https://www.sii.cl)
/ [Formato XML de Documentos Electrónicos](https://www.sii.cl/servicios_online/3532-formato_xml-3811.html)
as
"[Bajar schema XML de Documentos Tributarios Electrónicos](https://www.sii.cl/factura_electronica/factura_mercado/schema_dte.zip) (Incluye Documentos de exportación)"


## Contents


### Detail

- `DTE_v10.xsd`: "XSD principal y que incluye a los 3" otros XSD.
  - MD5: `907c199653dcf0f31a7bb06f8f0902ea`.
  - SHA256: `85518401b7dddac1bc0b7b99646a1ce353a4afa645344ea5f10af3a2e6676b37`
  - XML target namespace: `http://www.sii.cl/SiiDte`.
  - XML included/imported schemas: `SiiTypes_v10.xsd`, `xmldsignature_v10.xsd`.
  - XML elements:
    - `DTE`: (no description nor annotations)
  - XML data types:
    - `DTEDefType`: "Documento Tributario Electronico".

- `EnvioDTE_v10.xsd`: "descripción de documentos"
  - MD5: `44aa46d229dd7403617b2fe00d9a7e40`.
  - SHA256: `33ea8dd38c895c359dddbcd21feb5acf8a4717f7f67524a6b0dd9a83d76920eb`
  - XML target namespace: `http://www.sii.cl/SiiDte`.
  - XML included/imported schemas: `DTE_v10.xsd`, `xmldsignature_v10.xsd`.
  - XML elements:
    - `EnvioDTE`: "Envio de Documentos Tributarios Electronicos".
  - XML data types: none.

- `SiiTypes_v10.xsd`: "descripción de tipos de datos"
  - MD5: `b8f150bc7ee40425fe59b639566d9287`.
  - SHA256: `ce9a84bde70aa9d0f9269d99acd3b0ea81d868022517ac31064b6cdfa0c45bdf`
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
    - `HoraType`: "Hora entre 00:00:00 y 23:59:59".
    - `Dec16_2Type`: "Monto con 16 Digitos de Cuerpo y 2 Decimales".
    - `Dec14_4Type`: "Monto con 14 Digitos de Cuerpo y 4 Decimales".
    - `Dec14_4-0Type`: "Monto con 14 Digitos de Cuerpo y 4 Decimales partiendo de cero".
    - `Dec8_4Type`: "Monto con 8 Digitos de Cuerpo y 4 Decimales".
    - `Dec6_4Type`: "Monto con 6 Digitos de Cuerpo y 4 Decimales".
    - `Dec12_6Type`: "Monto con 12 Digitos de Cuerpo y 6 Decimales".
    - `PctType`: "Monto de Porcentaje ( 3 y 2)".
    - `TipoTransCOMPRA`: "Tipo de Transacción para el comprador".
    - `TipoTransVENTA`: "Tipo de Transacción para el vendedor".

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

- `DTE_v10.xsd` and `SiiTypes_v10.xsd` have LF line endings, while `EnvioDTE_v10.xsd` and
  `xmldsignature_v10.xsd` have CRLF ones, as in the original archive.
- `xmldsignature_v10.xsd` is identical to the one of version 2011-05-30.
- Among other changes, `DTE_v10.xsd` declares the fields that "Formato DTE" version 2.5 adds to
  `Transporte` (`PatenteCarro`, `FchSalida`, `HraSalida` and `FchLlegada`), in accordance with
  "Resolución Ex. SII N°154, 2025".
- Enums `DOCType`, `DocType`, `DTEType` and `DTEFacturasType` (all of them in `SiiTypes_v10.xsd`)
  are **very** similar.
