# Nuevo-en-SQL
 🧩 Contexto:
La empresa FinAdvisor Global desea implementar un sistema integral para la gestión de inversiones financieras personalizadas. Los clientes podrán crear uno o más portafolios, invertir en diversos instrumentos financieros (acciones, bonos, fondos, etc.) y consultar el rendimiento diario de sus inversiones. El sistema permitirá a asesores financieros y clientes visualizar la evolución de sus portafolios, analizar la rentabilidad, medir el riesgo, y generar reportes útiles para la toma de decisiones.

🎯 Objetivos del sistema:
Registrar portafolios financieros por cliente.

Controlar qué asesor financiero está a cargo de cada cliente.

Almacenar las inversiones realizadas dentro de cada portafolio.

Registrar transacciones de compra y venta por cada inversión.

Registrar el valor total del portafolio de forma diaria.

Calcular e interpretar indicadores clave como rentabilidad, riesgo, diversificación.

Permitir comparaciones históricas del valor del portafolio.

Detectar portafolios con bajo rendimiento o alta exposición a riesgo.

📦 Entidades clave (propuestas):
🧍 Cliente
ID_Cliente

Nombre

Correo

Teléfono

FechaRegistro

ID_Asesor (FK)

🧑‍💼 AsesorFinanciero
ID_Asesor

Nombre

Correo

Especialidad

💼 Portafolio
ID_Portafolio

Nombre

Tipo (Ej. Conservador, Moderado, Agresivo)

FechaCreacion

ID_Cliente (FK)

📈 InstrumentoFinanciero
ID_Instrumento

Nombre

Tipo (Ej. Acción, Bono, ETF)

Sector

País

Moneda

RiesgoEstimado

🧾 Inversión
ID_Inversion

ID_Portafolio (FK)

ID_Instrumento (FK)

FechaInicio

CantidadInvertidaInicial

🔁 Transacción
ID_Transaccion

ID_Inversion (FK)

Fecha

Tipo (Compra/Venta)

Monto

Cantidad

📅 ValorPortafolioDiario
ID_Valor

ID_Portafolio (FK)

Fecha

ValorTotal

📊 IndicadorDesempeño
ID_Indicador

ID_Portafolio (FK)

RentabilidadAnual (%)

NivelDiversificación (Bajo/Medio/Alto)

Volatilidad (%)

RiesgoGeneral (Bajo/Medio/Alto)

Clasificación (Ej. Estable, Riesgoso, Rentable)

📘 Reglas de negocio:
Cada cliente debe tener asignado un asesor financiero.

Un cliente puede tener múltiples portafolios activos.

Cada inversión está asociada a un único instrumento financiero.

Una inversión puede tener múltiples transacciones.

El valor total del portafolio se actualiza diariamente.

La rentabilidad anual se calcula en base a la evolución diaria del valor del portafolio.

Si el portafolio pierde más del 15% de su valor inicial, debe clasificarse como “Riesgoso”.

💡 Ejemplos de instrumentos financieros:
Acción: Apple Inc. (NASDAQ: AAPL)

Bono corporativo: Microsoft 5Y

Fondo indexado: S&P 500 ETF

Criptomoneda: Bitcoin (BTC)

🛠️ Posibles consultas:
¿Cuál fue el valor total del portafolio de cada cliente durante los últimos 30 días?

¿Qué instrumento financiero generó mayor rentabilidad para el cliente X en el último trimestre?

¿Qué portafolios tienen una diversificación baja y riesgo alto actualmente?

¿Cómo evolucionó el valor del portafolio “TechGrowth” desde su creación?

¿Cuántas transacciones hizo el cliente X este mes y en qué instrumentos?
