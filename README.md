# Análisis de Clientes RFM - AdventureWorks (PowerBI)

## Descripción del proyecto
Este proyecto presenta un análisis de clientes RFM (Recency, Monetary y Frequency) de la base de datos [**AdventureWork2019**](https://learn.microsoft.com/es-es/sql/samples/adventureworks-install-configure?view=sql-server-ver17&tabs=ssms)  (Venta de bicicletas y accesorios) de Microsoft.

- **Recency:** Recencia, corresponde al tiempo transcurrido desde la última compra realizada por el cliente. Para este proyecto, representado en días.
- **Frequency:** Frecuencia, corresponde a la frecuencia de compra realizada por los clientes en un periodo de tiempo determinado.
- **Monetary:** Valor del cliente, corresponde al total de valor monetario de las compras realizadas por el cliente en un periodo determinado.

## Objetivos del proyecto
- Realizar un análisis RFM de clientes en base a la data disponible del último año.
    - Calcular Recency y clasificar en estados.
    - Calcular Monetary y clasificar en estados.
    - Calcular Frequency y clasificar en estados.
    - Generar escala de niveles RFM considerando los estados definidos por cada una de las variables.
    - Generar gráficas para visualizar la distribución de clientes en base a la clasificación RFM. Permitiendo filtrar por tipo de cliente y la zona geográfica de ubicacion de estos.

## Stack Tecnológico
- SQL Server
- Power BI
- DAX
- Git/GitHub

## Modelo de Datos Análitico
Modelo basado en esquema estrella compuesto por:

- **FactCustomerMonthly:** Concentración de data de los clientes de los últimos 12 periodos (Cada periodo considera un mes, desde último periodo con ventas hacia atras). Considera fechas de primera y última venta, cantidad de ordenes y valor monetario total de ventas realizadas a cada cliente por cada periodo.
- **DimCustomerRFM:** Datos complementarios de clientes.
- **DimTerritoryRFM:** Datos complementarios de territorios geográficos. (Ubicación de los clientes)
- **DimDateRFM:** Datos complementarios de fechas de venta.

## Desarrollo
- Creación de nueva tabla mediante DAX para mantener un registro general del último año de cada cliente. Se incorpora la suma total de cantidad de ordenes y valor de venta total del último año.
- Se determinan niveles para clasificar a los clientes de acuerdo al total de Monetary y Frequency.
- Obtención de la última fecha de venta desde la tabla de hechos FactCustomerMonthly.
- Calculo de recency en días desde la última fecha de venta registrada del cliente hasta la fecha de corte (última fecha de venta disponible de todo el set de datos).
- Se determinan niveles de Recency por medio de quintiles.
- Se clasifica considerando las combinaciones de las 3 variables RFM.
- Se generan gráficas para visualizar la data cruzando Recency y Monetary. Es decir, la visualización de los niveles de Recency y el valor Monetary que representan esos clientes.
    - Se muestra por cada nivel de Recency, el total de Monetary representado para esos clientes.
    - Se incorpora gráfica para mostrar la diferencia del valor de ticket promedio de los niveles de Recency.
    - Gráfica para visualizar por cada nivel de Recency la distribución de acuerdo al nivel de Monetary.
-  Se generan gráficas para analizar Frequency y Monetary. Es decir, la visualización de la frecuencia de ventas realizadas a los clientes y el valor monetario que representan.
    - Mostrar la cantidad de clientes distribuidas por cada nivel de Frequency y Monetary, por medio de una matriz.
    - Mostrar el porcentaje de clientes por cada nivel de Frequency.
    - Mostrar el total de Monetary en base a los niveles de Monetary.
- Generación del visual de analisis de RFM.
    - Se genera tabla que permita visualizar por cada nivel de RFM el total de clientes, más el porcentaje total de clientes, Monetary total, porcentaje de Monetary del total y el valor de ticket promedio.
    - Se incorpora gráfica que permita ver el valor de Monetary por cada nivel RFM.
    - Se incorpora gráfica para visualizar la cantidad total de clientes clasificados de acuerdo al nivel RFM.
 
  ## Vistas previas de dashboards

>[!NOTE]
>
>Dentro del proyecto puede encontrar un archivo PDF con las páginas del informe de Power BI.
>

<img width="1414" height="790" alt="image" src="https://github.com/user-attachments/assets/0f8896e1-88f3-4f58-a073-c2465a6be8da" />
<img width="1413" height="792" alt="image" src="https://github.com/user-attachments/assets/b088ffe8-50d1-4393-aff6-33a920ae3633" />
<img width="1396" height="791" alt="image" src="https://github.com/user-attachments/assets/80fc89d5-4f27-4188-9934-921c81a3313c" />
<img width="1409" height="786" alt="image" src="https://github.com/user-attachments/assets/b0954f7e-edd4-40b5-81da-17f2b79c3630" />
<img width="1413" height="784" alt="image" src="https://github.com/user-attachments/assets/cd170c1f-e861-48a5-9dcc-15167e3305ab" />
<img width="1411" height="787" alt="image" src="https://github.com/user-attachments/assets/8752fd3f-28d6-4eb2-9e51-0f8f90c2f1be" />






     
