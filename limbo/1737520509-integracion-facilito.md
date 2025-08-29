---
id: 1737520509-integracion-facilito
aliases:
  - integracion facilito
tags: []
---

# Integracion facilito

## Cash in

### Deposito de Efectivo

#### Consulta de Cuentas de Cliente por Numero de Cedula

Método que devuelve la información que tiene la cuenta principal del cliente.

| Tipo | Nombre         | Dato    | Descripción     |
|------|----------------|---------|-----------------|
| In   | Cedula         | string  |                 |
| Out  | Resultado      | Numeric | 0 cuando es ok  |
| Out  | Mensaje        | string  |                 |
| Out  | Identificacion | string  |                 |
| Out  | IDcuenta       | string  | Id único cuenta |
| Out  | Nombre Titular | string  |                 |
| Out  | Descripcion    | string  |                 |

#### Método Deposito

Método por el cual se registra el depósito de un cliente.

| Tipo | Nombre          | Dato         | Descripción          |
|------|-----------------|--------------|----------------------|
| In   | Valor           | Numeric(12,2)|                      |
| In   | IDcuenta        | string       | Id único cuenta      |
| In   | Id Facilito     | Numeric      | Id generado FACILITO |
| Out  | Resultado       | Numeric      | 0 cuando es ok       |
| Out  | Mensaje         | string       |                      |
| Out  | Id Autorizacion | Numeric      | Id transacción IFI   |

### Cuotas de creditos

#### Método Consulta de Cuotas de Crédito por Número de Cédula

| Tipo | Nombre         | Tipo de Dato | Descripción      |
|------|----------------|--------------|------------------|
| In   | Cedula         | string       |                  |
| Out  | Resultado      | Numeric      | 0 cuando es ok   |
| Out  | Mensaje        | string       |                  |
| Out  | Nombre Titular | string       |                  |
| Out  | ID Credito     | string       | Id único crédito |
| Out  | Descripcion    | string       | Credito          |
| Out  | ValorMinimo    | Numeric      | Cuota mínima     |
| Out  | ValorTotal     | Numeric      | Valor pendiente  |

```json
{
  "CodioResultado": "000",
  "MensajeResultado": "Transaccion OK",
  "Nombre": "Ney arana",
  "DetalleCredito": [
    {
      "IDCredito": "12764",
      "Descripcion": "Credito Estudiantil",
      "ValorMinimo": "100.20",
      "ValorTotal": "4678.23”
    },
    {
      "IDCredito": "12765",
      "Descripcion": "Credito Vivienda",
      "ValorMinimo": "100.20",
      "ValorTotal": "4678.23”
    },
    {
      "IDCredito": "1276456",
      "Descripcion": "Credito Vehicular",
      "ValorMinimo": "100.20",
      "ValorTotal": "4678.23”
    }
  ]
}
```

#### Método Recaudación de Cuota de Crédito

Método por el cual se registra un pago a las cuotas de los préstamos de un cliente.

| Tipo | Nombre          | Dato    | Descripción          |
|------|-----------------|---------|----------------------|
| In   | ID Credito      | string  | Id único crédito     |
| In   | Valor           | Numeric |                      |
| In   | Id Facilito     | Numeric | Id generado FACILITO |
| Out  | Resultado       | Numeric | 0 cuando es ok       |
| Out  | Mensaje         | string  | Resultado            |
| Out  | Id Autorizacion | Numeric | Id transacción IFI   |

## Cash Out

### Retiro de Efectivo

#### Método Consulta de Cuenta de Cliente por Numero de Cedula

Método que devuelve la información que tiene la cuenta principal del cliente.

| Tipo | Nombre         | Dato    | Descripción     |
|------|----------------|---------|-----------------|
| In   | Cedula         | string  |                 |
| Out  | Resultado      | Numeric | 0 cuando es ok  |
| Out  | Mensaje        | string  |                 |
| Out  | Identificacion | string  |                 |
| Out  | IDcuenta       | string  | Id único cuenta |
| Out  | Nombre Titular | string  |                 |
| Out  | Descripcion    | string  |                 |

#### Método Solicitud de OTP

Método que permite validar las transacciones de CashOut
Facilito enviará el requerimiento de generación de la OTP para que el Autorizador
envié por correo/SMS/otros medios el código generado al cliente.

| Tipo | Nombre         | Dato    | Descripción     |
|------|----------------|---------|-----------------|
| In   | IDcuenta       | string  | Id único cuenta |
| In   | Valor          | Numeric |                 |
| Out  | Resultado      | Numeric | 0 cuando es ok  |
| Out  | Mensaje        | string  | Resultado       |

#### Método Retiro

Método que permite registrar un debito en a la cuenta del cliente por medio de
un retiro.

| Tipo | Nombre          | Dato    | Descripción            |
|------|-----------------|---------|------------------------|
| In   | IDcuenta        | string  | Id único cuenta        |
| In   | OTP             | string  |                        |
| In   | Valor           | Numeric |                        |
| In   | TipoOperacion   | string  | RETIRO, PAGO_SERVICIOS |
| In   | Id Facilito     | Numeric | Id generado FACILITO   |
| Out  | Resultado       | Numeric | 0 cuando es ok         |
| Out  | Mensaje         | string  | Resultado              |
| Out  | Id Autorizacion | Numeric | Id transacción IFI     |

### Reverso de transacciones

#### Método Reverso

Método que permite reversar o anular una transacción

| Tipo | Nombre          | Dato    | Descripción          |
|------|-----------------|---------|----------------------|
| In   | Valor Pagar     | Numeric | Valor enviado pago   |
| In   | Id Facilito     | Numeric | Id generado FACILITO |
| Out  | Resultado       | Numeric | 0 cuando es ok       |
| Out  | Mensaje         | string  | Resultado            |
