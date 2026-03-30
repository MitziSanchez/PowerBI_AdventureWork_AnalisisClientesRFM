# Análisis de Clientes RFM - AdventureWorks (PowerBI)

## Descripción del proyecto
Este proyecto presenta un análisis de clientes RFM (Recency, Monetary y Frequency) de la base de datos [**AdventureWork2019**](https://learn.microsoft.com/es-es/sql/samples/adventureworks-install-configure?view=sql-server-ver17&tabs=ssms)  (Venta de bicicletas y accesorios) de Microsoft.

- **Recency:** Recencia, corresponde al tiempo transcurrido desde la última compra realizada por el cliente. (En este proyecto se representa en días).
- **Frequency:** Frecuencia, corresponde a la frecuencia de compra realizada por los clientes en un período de tiempo determinado.
- **Monetary:** Valor del cliente, corresponde al total de valor monetario de las compras realizadas por el cliente en un período determinado.

## Objetivos del proyecto
- Realizar un análisis RFM de clientes en base a los datos disponible del último año.
    - Calcular Recency, monetary y frequency. Clasificar en estados.
    - Generar escala de niveles RFM considerando el cruce de las variables anteriores.
    - Generar gráficas para visualizar la distribución de clientes y la concentración de ingresos por venta que representan en base a la clasificación RFM. 

## Stack Tecnológico
- SQL Server
- Power BI
- DAX
- Git/GitHub

## Modelo de Datos Análitico
Modelo basado en esquema estrella compuesto por:

- **FactCustomerMonthly:** Resumen de los últimos 12 períodos de las ventas de los clientes (Cada período considera un mes, desde último período con ventas hacia atrás). Considera fechas de primera y última venta, cantidad de ordenes y valor monetario del total de ventas realizadas a cada cliente por cada período.
- **DimCustomerRFM:** Datos complementarios de clientes.
- **DimTerritoryRFM:** Datos complementarios de territorios geográficos. (Ubicación de los clientes)
- **DimDateRFM:** Datos complementarios de fechas de venta.

## Desarrollo
- Creación de nueva tabla mediante DAX para mantener un registro general del último año de cada cliente. Se incorpora la suma total de cantidad de ordenes y valor de venta total del último año.
- Se determinan niveles para clasificar a los clientes de acuerdo al total de Monetary y Frequency.
- Obtención de la última fecha de venta desde la tabla de hechos FactCustomerMonthly.
- Calculo de Recency en días desde la última fecha de venta registrada del cliente hasta la fecha de corte (última fecha de venta disponible de todo el set de datos).
- Se determinan niveles de Recency por medio de quintiles.
- Se clasifica a los clientes considerando las combinaciones de las 3 variables RFM.
- Se generan gráficas para visualizar los datos de acuerdo a los niveles de Recency y el valor Monetary. Es decir, la visualización de los niveles de recencia y el valor monetario que representan  
    - Se muestra la monetary total por cada nivel de recency.
    - Se incorpora gráfica para mostrar la diferencia del valor de ticket promedio de los niveles de Recency.
    - Gráfica para visualizar la distribución porcentual de la monetary total de cada estado de recency, de acuerdo a los niveles de monetary.
-  Se generan gráficas para analizar Frequency y Monetary. Es decir, la visualización de la frecuencia de ventas realizadas a los clientes y el valor monetario que representan.
    - Mostrar la cantidad de clientes distribuidos por cada nivel de Frequency y Monetary, por medio de una matriz.
    - Mostrar el porcentaje de clientes por cada nivel de Frequency.
    - Mostrar el total de Monetary en base a los niveles de Monetary.
- Generación del visual de análisis de RFM (Cruce de las 3 variables).
    - Se genera tabla que permita visualizar por cada nivel de RFM el total de clientes, más el porcentaje total de clientes, Monetary total, porcentaje de Monetary del total y el valor de ticket promedio.
    - Se incorpora gráfica que permita ver el valor de Monetary por cada nivel RFM.
    - Se incorpora gráfica para visualizar la cantidad total de clientes clasificados de acuerdo al nivel RFM.
 
  ## Vistas previas de dashboards

>[!NOTE]
>
>Dentro del proyecto puede encontrar un archivo PDF con las páginas del informe de Power BI.
>

<img width="1409" height="791" alt="image" src="https://github.com/user-attachments/assets/b38cd7a5-5544-4089-9ccd-a2abe4755187" />
<img width="1410" height="794" alt="image" src="https://github.com/user-attachments/assets/4efde629-fe93-48aa-96ba-bd1e0d60e638" />
<img width="1398" height="786" alt="image" src="https://github.com/user-attachments/assets/38b52aa5-bb4b-47b7-a209-38bfa40953b4" />
<img width="1414" height="784" alt="image" src="https://github.com/user-attachments/assets/68ef0d2b-504c-4213-9f5d-978ebff666f4" />
<img width="1415" height="789" alt="image" src="https://github.com/user-attachments/assets/93d8de47-2194-4ac6-9187-90f13e470fbd" />
<img width="1413" height="794" alt="image" src="https://github.com/user-attachments/assets/21eb4975-50fb-450f-b4d4-79226a580098" />












     
