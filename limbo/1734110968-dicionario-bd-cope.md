---
id: 1734110968-dicionario-bd-cope
aliases:
  - Dicionario BD Cope
tags: []
---

# Dicionario BD Coperativa

## FBS_CAJAS

### BOVEDA

**DESCRIPCIÓN**: Datos de bóvedas para concentración de valores por oficina.

| **Campo**                    | **Tipo de Dato** | **Descripción**|
|------------------------------|------------------|----------------|
| **SECUENCIAL**               | `int`            | Primary Key    |
| **SECUENCIALOFICINA**        | `int`            | Obligatorio    |
| **CODIGOUSUARIORESPONSABLE** | `nvarchar(25)`   | Obligatorio    |
| **ESTAACTIVA**               | `bit`            | Obligatorio    |
| **NUMEROVERIFICADOR**        | `int`            | Obligatorio    |
| **EXISTENCIAMINIMA**         | `decimal(18,2)`  | Obligatorio    |
| **EXISTENCIAMAXIMA**         | `decimal(18,2)`  | Obligatorio    |

### BOVEDA_HISTORICOACTIVACION

**DESCRIPCIÓN**: Datos de bóvedas históricos Activación por usuario.

| **Campo**           | **Tipo de Dato** | **Descripción**|**FK**           |
|---------------------|------------------|----------------|-----------------|
| **SECUENCIAL**      | `int`            | Primary Key    |                 |
| **SECUENCIALBOVEDA**| `int`            | Obligatorio    |[BOVEDA](#boveda)|
| **BOVEDAACTIVA**    | `bit`            | Obligatorio    |                 |
| **FECHASISTEMA**    | `datetime`       | Obligatorio    |                 |
| **FECHAMAQUINA**    | `datetime`       | Obligatorio    |                 |

## FBS_CAPTACIONESVISTA

### CUENTACLIENTE

**DESCRIPCIÓN**: Registra datos de cuentas de clientes.

| **Campo**           | **Tipo de Dato** | **Descripción**|**FK**|
|---------------------|------------------|----------------|------|
| **SECUENCIAL**      | `int`            | Primary Key    |      |
| **SECUENCIALCUENTA**| `int`            | Obligatorio    | [CUENTAMAESTRO](#cuentamaestro)|
| **SECUENCIALCLIENTE**| `int`           | Obligatorio    | [CLIENTE](#cliente)|
| **ESPRINCIPAL**     | `bit`            | Obligatorio    |      |
| **ESTAACTIVO**      | `bit`            | Obligatorio    |      |
| **NUMEROVERIFICADOR**| `int`           | Obligatorio    |      |

### CUENTAMAESTRO

**DESCRIPCIÓN**: Registra datos de cuentas maestras.

| **Campo**                       | **Tipo de Dato** | **Descripción**|**FK**|
|---------------------------------|------------------|----------------|------|
| **SECUENCIAL**                  | `int`            | Primary Key    |      |
| **CODIGO**                      | `nvarchar(20)`   | Obligatorio    |      |
| **CODIGOTIPOCUENTA**            | `nvarchar(20)`   | Obligatorio    |      |
| **CODIGOPRODUCTOVISTA**         | `nchar(20)`      | Obligatorio    |      |
| **CODIGOESTADO**                | `nvarchar(1)`    | Obligatorio    |      |
| **SECUENCIALMONEDA**            | `int`            | Obligatorio    |      |
| **SECUENCIALOFICINA**           | `int`            | Obligatorio    |      |
| **CODIGOUSUARIOOFICIAL**        | `nvarchar(25)`   | Obligatorio    |      |
| **FECHASISTEMACREACION**        | `datetime`       | Obligatorio    |      |
| **FECHAMAQUINACREACION**        | `datetime`       | Obligatorio    |      |
| **NUMEROLIBRETA**               | `int`            | Obligatorio    |      |
| **NUMEROLINEAIMPRIMELIBRETA**   | `int`            | Obligatorio    |      |
| **ESANVERSO**                   | `bit`            | Obligatorio    |      |
| **TIENESEGUROACTIVO**           | `bit`            | Obligatorio    |      |
| **BLOQUEADATRANSACCIONOPERATIVA**| `bit`          | Obligatorio    |      |
| **NUMEROVERIFICADOR**           | `int`            | Obligatorio    |      |
| **TRABAJACONTALONARIO**         | `bit`            | Obligatorio    |      |
| **FECHACORTE**                  | `datetime`       | Obligatorio    |      |
| **SECUENCIALCLIENTEPRINCIPAL**  | `int`            | Obligatorio    |      |
| **CODIGOORIGINAL**              | `nvarchar(20)`   | Obligatorio    |      |
| **SECMIGRA**                    | `int`            | Obligatorio    |      |

### TIPOCUENTA

**DESCRIPCIÓN**: Registra los tipos de cuentas que se pueden tener.

| **Campo**                       | **Tipo de Dato** | **Descripción**|
|---------------------------------|------------------|----------------|
| **SECUENCIAL**                  | `int`            | Primary Key    |
| **CODIGO**                      | `nvarchar(20)`   | Obligatorio    |
| **NOMBRE**                      | `nvarchar(50)`   | Obligatorio    |
| **SIGLAS**                      | `nvarchar(3)`    | Obligatorio    |
| **ESOPERATIVO**                 | `bit`            | Obligatorio    |
| **SECUENCIALEMPRESA**           | `int`            | Obligatorio    |
| **ACEPTAMULTICUENTA**           | `bit`            | Obligatorio    |
| **ACEPTASOBREGIROAUTOMATICO**   | `bit`            | Obligatorio    |
| **PROVISIONAINTERES**           | `bit`            | Obligatorio    |
| **SALDOMINIMO**                 | `decimal(18,2)`  | Obligatorio    |
| **ESTAACTIVO**                  | `bit`            | Obligatorio    |
| **NUMEROVERIFICADOR**           | `int`            | Obligatorio    |
| **ESAHORROPROGRAMADO**          | `bit`            | Obligatorio    |
| **ACEPTATALONARIO**             | `bit`            | Obligatorio    |
| **ESENCAJE**                    | `bit`            | Obligatorio    |

## FBS_CLIENTES

### CLIENTE

**DESCRIPCIÓN**: Registra datos de clientes de la cooperativa.

| **Campo**                | **Tipo de Dato** | **Descripción**|**FK**|
|--------------------------|------------------|----------------|------|
| **SECUENCIAL**           | `int`            | Primary Key    |      |
| **SECUENCIALOFICINA**    | `int`            | Obligatorio    |      |
| **SECUENCIALPERSONA**    | `int`            | Obligatorio    | [PERSONA](#persona)|
| **NUMEROCLIENTE**        | `int`            | Obligatorio    |      |
| **FECHAINGRESO**         | `datetime`       | Obligatorio    |      |
| **NUMEROVERIFICADOR**    | `int`            | Obligatorio    |      |
| **CODIGOUSUARIOOFICIAL** | `nvarchar(25)`   | Obligatorio    |      |
| **SECMIGRA**             | `int`            | Obligatorio    |      |

## FBS_GENERALES

### DIVISION

**DESCRIPCIÓN**: Registra datos de divisiones.

| **Campo**           | **Tipo de Dato** | **Descripción**|
|---------------------|------------------|----------------|
| **SECUENCIAL**      | `int`            | Primary Key    |
| **SECUENCIALNIVEL** | `int`            | Obligatorio    |
| **CODIGO**          | `nvarchar(20)`   | Obligatorio    |
| **NOMBRE**          | `nvarchar(4000)` | Obligatorio    |
| **NUMEROVERIFICADOR**| `int`           | Obligatorio    |

### PAIS

DESCRIPCIÓN: Registra datos de países.

| **Campo**                       | **Tipo de Dato** | **Descripción**|
|---------------------------------|------------------|----------------|
| **SECUENCIAL**                  | `int`            | Primary Key    |
| **CODIGO**                      | `nvarchar(10)`   | Obligatorio    |
| **NOMBRE**                      | `nvarchar(50)`   | Obligatorio    |
| **SECUENCIALTIPODIVISIONPOLITICA**| `int`          | Obligatorio    |
| **ESTAACTIVO**                  | `bit`            | Obligatorio    |
| **NUMEROVERIFICADOR**           | `int`            | Obligatorio    |
| **CODIGONACIONALIDAD**          | `nvarchar(10)`   | Optional       |
| **CODIGOSRI**                   | `nvarchar(10)`   | Optional       |
| **CODIGOSEPS**                  | `nchar(10)`      | Optional       |

## FBS_PERSONAS

### PERSONA

**DESCRIPCIÓN**: Registra datos de personas, se toma como referencia para la
creación de cuentas.

| **Campo**                       | **Tipo de Dato** | **Descripción**|**FK**|
|---------------------------------|------------------|----------------|------|
| **SECUENCIAL**                  | `int`            | Primary Key    |      |
| **IDENTIFICACION**              | `nvarchar(20)`   | Obligatorio    |      |
| **NOMBREUNIDO**                 | `nvarchar(200)`  | Obligatorio    |      |
| **DIRECCIONDOMICILIO**          | `nvarchar(500)`  | Obligatorio    |      |
| **REFERENCIADOMICILIARIA**      | `nvarchar(600)`  | Obligatorio    |      |
| **EMAIL**                       | `nvarchar(70)`   | Obligatorio    |      |
| **SECUENCIALTIPOIDENTIFICACION**| `int`            | Obligatorio    | [TIPOIDENTIFICACION](#tipoidentificacion)|
| **SECUENCIALDIVPOLRESIDENCIA**  | `int`            | Obligatorio    | [DIVISION](#division)|
| **CODIGOPAISORIGEN**            | `nvarchar(10)`   | Obligatorio    | [PAIS](#pais)|
| **NUMEROVERIFICADOR**           | `int`            | Obligatorio    |       |
| **SECUENCIALDIVACTIVIDADECON**  | `int`            | Obligatorio    | [DIVISION](#division)|
| **FECHAULTIMAACTUALIZACION**    | `datetime`       | Obligatorio    |       |
| **CODIGOUSUARIOACTUALIZA**      | `nvarchar(25)`   | Obligatorio    |       |
| **SECMIGRA**                    | `int`            | Obligatorio    |       |

### PERSONA_NATURAL

**DESCRIPCIÓN**: Registra datos de personas naturales.

| **Campo**                       | **Tipo de Dato** | **Descripción**|**FK**|
|---------------------------------|------------------|----------------|------|
| **SECUENCIALPERSONA**            | `int`            | Primary Key    |[PERSONA](#persona)|
| **APELLIDOS**                    | `nvarchar(100)`  | Obligatorio    |      |
| **NOMBRES**                      | `nvarchar(100)`  | Obligatorio    |      |
| **FECHANACIMIENTO**              | `datetime`       | Obligatorio    |      |
| **ESMASCULINO**                  | `bit`            | Obligatorio    |      |
| **CODIGOESTADOCIVIL**            | `nchar(1)`       | Obligatorio    |      |
| **CODIGOTIPOEDUCACION**          | `nchar(1)`       | Obligatorio    |      |
| **CODIGOTIPOVIVIENDA**           | `nchar(1)`       | Obligatorio    |      |
| **CODIGOPROFESION**              | `nchar(4)`       | Obligatorio    |      |
| **APELLIDOPATERNO**              | `nvarchar(80)`   | Obligatorio    |      |
| **APELLIDOMATERNO**              | `nvarchar(80)`   | Obligatorio    |      |
| **LUGARNACIMIENTO**              | `nvarchar(500)`  | Obligatorio    |      |
| **NUMEROPAPELETAVOTACION**       | `nvarchar(10)`   | Obligatorio    |      |
| **CARGASFAMILIARES**             | `int`            | Obligatorio    |      |
| **BAJOMODALIDADDATOSMINIMOS**    | `bit`            | Obligatorio    |      |
| **NUMEROMESESVIVIENDA**          | `int`            | Obligatorio    |      |

### PERSONA_NATURALOCUPACION

**DESCRIPCIÓN**: Registra las ocupaciones de las personas naturales.

| **Campo**                       | **Tipo de Dato** | **Descripción**|**FK**|
|---------------------------------|------------------|----------------|------|
| **SECUENCIAL**                  | `int`            | Primary Key    |      |
| **SECUENCIALPERSONANATURAL**    | `int`            | Obligatorio    |[PERSONA_NATURAL](#persona_natural)|
| **DESCRIPCIONOCUPACION**        | `nvarchar(250)`  | Obligatorio    |      |
| **DIRECCION**                   | `nvarchar(250)`  | Obligatorio    |      |
| **INGRESOMENSUALOCUPACION**     | `decimal(18,2)`  | Obligatorio    |      |
| **FECHAINICIO**                 | `datetime`       | Obligatorio    |      |
| **SECUENCIALDIVPOLUBICACION**   | `int`            | Obligatorio    |      |
| **ESTAACTIVA**                  | `bit`            | Obligatorio    |      |
| **NUMEROVERIFICADOR**           | `int`            | Obligatorio    |      |
| **SECUENCIALDIVACTIVIDADECON**  | `int`            | Obligatorio    |      |
| **ESPRINCIPAL**                 | `bit`            | Obligatorio    |      |
| **LUGARTRABAJO**                | `nvarchar(250)`  | Obligatorio    |      |
| **CARGO**                       | `nvarchar(100)`  | Obligatorio    |      |
| **TIENEANTERIORTRABAJO**        | `bit`            | Obligatorio    |      |
| **FECHAINICIOANTERIORTRABAJO**  | `datetime`       | Obligatorio    |      |
| **FECHASALIDAANTERIORTRABAJO**  | `datetime`       | Obligatorio    |      |
| **ESSUELDOBAJOROL**             | `bit`            | Obligatorio    |      |
| **TELEFONOTRABAJO**             | `nchar(10)`      | Obligatorio    |      |

### TELEFONOPERSONA

**DESCRIPCIÓN**: Registra los teléfonos de las personas.

| **Campo**                  | **Tipo de Dato**| **Descripción**|**FK** |
|----------------------------|-----------------|----------------|-------|
| **SECUENCIAL**             | `int`           | Primary Key    |       |
| **SECUENCIALPERSONA**      | `int`           | Obligatorio    | [PERSONA](#persona)|
| **CODIGOEMPRESATELEFONICA**| `nchar(3)`      | Obligatorio    |       |
| **CODIGOTIPOTELEFONO**     | `nchar(1)`      | Obligatorio    |       |
| **NUMEROTELEFONO**         | `nvarchar(20)`  | Obligatorio    |       |
| **DESCRIPCION**            | `nvarchar(100)` | Obligatorio    |       |
| **ESTAACTIVO**             | `bit`           | Obligatorio    |       |
| **NUMEROVERIFICADOR**      | `int`           | Obligatorio    |       |
| **RECIBENOTIFICACION**     | `bit`           | Obligatorio    |       |

### TIPOIDENTIFICACION

**DESCRIPCIÓN**: Registra los tipos de identificación que se pueden tener.

| **Campo**                       | **Tipo de Dato** | **Descripción**|
|---------------------------------|------------------|----------------|
| **SECUENCIAL**                  | `int`            | Primary Key    |
| **CODIGO**                      | `nvarchar(10)`   | Obligatorio    |
| **NOMBRE**                      | `nvarchar(50)`   | Obligatorio    |
| **PARAPERSONANATURAL**          | `bit`            | Obligatorio    |
| **NUMEROMINIMOREPRESENTANTE**   | `int`            | Obligatorio    |
| **NUMEROMINIMOREFERENCIASPERSONA**| `int`          | Obligatorio    |
| **NUMEROMINIMOREFERENCIASBANCARI**| `int`          | Obligatorio    |
| **NUMEROMINIMOREFERENCIASCOMERCI**| `int`          | Obligatorio    |
| **NUMEROMINIMOTELEFONOS**       | `int`            | Obligatorio    |
| **ESTAACTIVA**                  | `bit`            | Obligatorio    |
| **NUMEROVERIFICADOR**           | `int`            | Obligatorio    |
| **NUMEROMINIMODIRECCION**       | `int`            | Obligatorio    |
| **CODIGOSBS**                   | `nvarchar(1)`    | Obligatorio    |
