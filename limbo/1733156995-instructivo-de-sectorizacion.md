---
id: 1733156995-instructivo-de-sectorizacion
aliases:
  - instructivo de sectorizacion
tags: []
---

# Instructivo de sectorizacion

## Glosario de terminos

- BCE: Banco Central del Ecuador.
- FTP: File Transfer Protocol. Protocolo de transferencia de archivo.
- IESS: Instituto de Seguridad Social
- ISSFA: Instituto de Seguridad Social de las Fuerzas Armadas
- ISSPOL: Instituto de Seguridad Social de la Policía Nacional
- Matriz de sectorización: es un detalle de determinadas cuentas sectorizadas que se clasifican
  por sector institucional: Gobierno Central, gobiernos provinciales y locales, fondos de la
  seguridad social, Banco Central, empresas públicas, otras sociedades financieras, otros
  intermediarios financieros, auxiliares financieros, off-shore, empresas, hogares y no residentes.
  Sirve el control de los archivos sectorizados que envía el sistema financiero nacional. Incluye
  banderas o marcas en los sectores institucionales por cada cuenta para impedir que las
  entidades financieras registren en forma errónea los valores.
- RUC: Registro Único de Contribuyentes.
- SB: Superintendencia de Bancos.
- SEPS: Superintendencia de Economía Popular y Solidaria.

## CLASIFICACIÓN DE SECTORES Y SUBSECTORES

### SECTORIZACIÓN INSTITUCIONAL DE LA ECONOMÍA

#### SECTOR PÚBLICO (11)

#### GOBIERNO CENTRAL (111)

#### FONDOS DE LA SEGURIDAD SOCIAL (112)

- IESS
- ISSFA
- ISSPOL

#### EMPRESAS PÚBLICAS NO FINANCIERAS (113)

#### GOBIERNOS PROVINCIALES Y LOCALES (114)

### SECTOR SOCIEDADES FINANCIERAS (12)

La intermediación es una actividad en la que una unidad institucional (como un banco o una cooperativa) capta fondos mediante la contracción de pasivos (deudas) por cuenta propia. El objetivo es canalizar estos fondos hacia otras unidades institucionales mediante préstamos o adquiriendo activos financieros.

#### BANCO CENTRAL DEL ECUADOR (121)

#### SOCIEDADES DE DEPÓSITO (122)

#### OTROS INTERMEDIARIOS FINANCIEROS (123)

#### AUXILIARES FINANCIEROS Y COMPAÑÍAS DE SEGUROS (124)

- Auxiliares financieros: Son unidades que ofrecen servicios especializados
  relacionados con la intermediación financiera, pero no captan fondos ni
  otorgan créditos por cuenta propia.

- Compañías de seguros: Son entidades que proporcionan beneficios financieros
  a personas y empresas en casos de accidentes, enfermedades y otras
  eventualidades, según los servicios que ofrecen.

- Nota: Este subsector incluye seguros, reaseguros y fondos de pensiones.

#### OFF-SHORE (125)

### SECTOR PRIVADO (13)

Este sector comprende las sociedades que no están controladas por el gobierno
y las familias.

#### EMPRESAS (131)

#### HOGARES (132)

### NO RESIDENTES (140)

Corresponde a los sectores cuyo centro de interés económico se encuentra fuera
de las fronteras del país.

## ENVÍO DE INFORMACIÓN DE SECTORIZACIÓN AL BANCO CENTRAL DEL ECUADOR

Se utiliza la “Matriz de sectorización institucional de los registros
contables del sistema financiero nacional”.
La información de la matriz de sectorización y el balance correspondiente
serán enviados al Banco Central del Ecuador **cada semana**. Se deben remitir en
un plazo de dos días, con **datos del último día laborable de la semana anterior**,
considerará como incumplimiento si no se presenta **conjuntamente el balance y
la matriz de sectorización**.

## INFORMACIÓN CONTABLE Y DE SECTORIZACIÓN

### FORMATO PARA ENTREGA DE ANEXO A BALANCES

#### FORMATO DEL REGISTRO CABECERA

| Campo        | C. estructura | C. entidad   | F. datos    | NT. registros | V. cuadre      |
| ------------ | ------------- | ------------ | ----------- | ------------- | -------------- |
| Tipo de dato | Carácter (3)  | Carácter (4) | Fecha       | Numerico(4)   | Numerico(18,2) |
| Opción       | Obligatorio   | Obligatorio  | Obligatorio | Obligatorio   | Obligatorio    |

- Código de la estructura (Obligatorio).- codificación dada a la estructura de Anexo
  Sectorización Institucional, la cual será SEC.
- Código de entidad (Obligatorio).- codificación dada por la SB y la SEPS a cada entidad
  financiera.
- Fecha de datos (Obligatorio).- fecha de corte de la información enviada.
- Número total de registros (Obligatorio).- número de líneas que contiene el archivo incluido
  el registro de cabecera.
- Valor de cuadre (Obligatorio).- representa la suma algebraica de todos los valores de saldo
  por sector de los registros de detalle. Este valor vendrá expresado en unidades de dólar con
  centavos (2) bajo el formato: Numérico (18,2)

#### FORMATO DEL REGISTRO DETALLE

| Campo        | CC. contable | CS. institucional | S. sector      |
| ------------ | ------------ | ----------------- | -------------- |
| Tipo de dato | Numerico(8)  | Caracter(6)       | Numerico(18,2) |
| Opción       | Obligatorio  | Obligatorio       | Obligatorio    |
| Tabla        |              | Tabla 1           |                |

- Código cuenta contable (Obligatorio).- codificación dada a cada una de las cuentas
  contables del catálogo designado por la SB y la SEPS para entidades financieras.
- Código sector institucional (Obligatorio).- codificación dada a cada sector institucional de
  acuerdo a la tabla.
- Saldo por sector (Obligatorio).- valor numérico, representa el saldo que dispone la entidad
  en un sector institucional en cada una de las cuentas contables expresado en unidades de
  dólar con centavos (2) bajo el formato: Numérico (18,2).

#### DEFINICIÓN DEL NOMBRE DEL ARCHIVO

- **Nombre del archivo**: CCCPEEEEDDMMAAAA.txt

| Dato | Descripcion                  | Longitud |
| ---- | ---------------------------- | -------- |
| CCC  | Estructura de datos          | 3        |
| P    | Periodicidad                 | 1        |
| EEEE | Código de entidad            | 4        |
| DD   | Día de fecha de datos        | 2        |
| MM   | Mes de fecha de datos        | 2        |
| AAAA | Año de fecha de datos        | 4        |
| Txt  | Fijo (Extensión del archivo) | 3        |

- Ejemplo: SECD102931052015.txt
  - SEC: identificación de la estructura de datos enviada
  - D: periodicidad semanal y de fin de mes
  - 1029: Banco Pichincha
  - 31: día 31
  - 05: mes mayo
  - 2015: año 2015
  - Txt: extensión del archivo
