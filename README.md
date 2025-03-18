### Descripción del Proyecto: Análisis de los Planes Prepagos de Megaline (Surf vs. Ultimate)

#### **1. Introducción**

Este proyecto se centra en analizar el desempeño de los dos planes prepagos de Megaline: **Surf** y **Ultimate**. El objetivo es comparar el comportamiento de los clientes a través de diferentes aspectos, como **uso de llamadas**, **mensajes de texto**, **uso de datos de internet** e **ingresos mensuales**. Además, el análisis prueba dos hipótesis clave sobre las diferencias en **ingresos entre los dos planes** y los **ingresos de los usuarios en la región NY-NJ en comparación con otras regiones**. A través de este análisis, se busca entender cómo se comporta cada plan en términos de patrones de uso y generación de ingresos, proporcionando valiosos conocimientos para las decisiones estratégicas de Megaline.

#### **2. Resumen de los Datos**

Los datos utilizados en este análisis consisten en múltiples DataFrames relacionados con el comportamiento del cliente, con los siguientes componentes clave:
- **df_calls**: Contiene datos de uso de llamadas (137,735 filas, 4 columnas).
- **df_internet**: Contiene datos de uso de internet (104,825 filas, 4 columnas).
- **df_messages**: Contiene datos de uso de mensajes (76,051 filas, 3 columnas).
- **df_plans**: Contiene detalles de los planes (2 filas, 8 columnas).
- **df_users**: Contiene datos demográficos de los usuarios (500 filas, 8 columnas).

Los datos necesitaban ser limpiados, alineados y fusionados entre estos diferentes DataFrames para crear un conjunto de datos unificado para el análisis.

#### **3. Procedimientos**

##### **3.1 Limpieza y Preparación de los Datos**

- **Manejo de Datos Faltantes**: Los DataFrames eran bastante limpios, sin valores NaN o duplicados significativos. Sin embargo, se encontraron problemas en las **columnas de fecha**, que tenían tipos de datos incorrectos. Estos fueron corregidos para asegurar un análisis adecuado.
  
- **Fusión de Datos**: Los diferentes DataFrames fueron fusionados en un solo conjunto de datos integral para facilitar el análisis de diferentes variables como **llamadas**, **mensajes**, **uso de internet** e **ingresos mensuales**.

- **Transformación de Datos**: Se transformaron las columnas según fuera necesario, como redondear valores numéricos y agrupar los datos por mes o por usuario para facilitar las comparaciones.

##### **3.2 Análisis Exploratorio de Datos (EDA)**

- **Estadísticas Descriptivas**: Para ambos planes **Surf** y **Ultimate**, se calcularon la media, la varianza y la desviación estándar para **mensajes**, **uso de datos de internet** e **ingresos mensuales**.
  
- **Visualizaciones**: Se crearon varias visualizaciones para representar los datos, como histogramas y gráficos de barras, para mostrar la distribución de **mensajes**, **uso de datos de internet** e **ingresos mensuales** para ambos planes. Esto ayudó a identificar patrones y tendencias a lo largo del tiempo y entre los planes.

##### **3.3 Pruebas de Hipótesis**

Se probaron dos hipótesis:
1. **Hipótesis 1**: El ingreso promedio de los usuarios de los planes **Surf** y **Ultimate** es diferente.
   - **Hipótesis Nula (H₀)**: El ingreso promedio de los usuarios de los planes **Surf** y **Ultimate** es igual.
   - **Hipótesis Alternativa (H₁)**: El ingreso promedio de los usuarios de los planes **Surf** y **Ultimate** es diferente.

   Se realizó una prueba t y se **rechazó la hipótesis nula**, lo que indica que los ingresos promedio entre los dos planes eran significativamente diferentes.

2. **Hipótesis 2**: El ingreso promedio de los usuarios en la región **NY-NJ** es diferente del ingreso promedio de los usuarios en otras regiones.
   - **Hipótesis Nula (H₀)**: El ingreso promedio de los usuarios en la región **NY-NJ** es igual al ingreso promedio de los usuarios en otras regiones.
   - **Hipótesis Alternativa (H₁)**: El ingreso promedio de los usuarios en la región **NY-NJ** es diferente al ingreso promedio de los usuarios en otras regiones.

   Se realizó una prueba t y **no se rechazó la hipótesis nula**, sugiriendo que no hay una diferencia significativa en los ingresos promedio entre los usuarios de la región **NY-NJ** y los de otras regiones.

#### **4. Hallazgos**

##### **4.1 Análisis de Mensajes y Uso de Internet**
- **Mensajes**: 
   - Los usuarios del plan **Surf** tienden a exceder su límite mensual de mensajes con mayor frecuencia que los usuarios del plan **Ultimate**. La distribución de mensajes fue **sesgada a la derecha**, lo que indica que la mayoría de los usuarios de ambos planes no usan mensajes de manera frecuente.
   - Los usuarios del plan **Ultimate** generalmente se mantienen dentro de los límites, y su uso es más predecible.

- **Uso de Internet**:
   - El uso promedio de datos en ambos planes fue relativamente similar, con los usuarios de **Surf** promediando **16.78 GB** y los usuarios de **Ultimate** promediando **17.37 GB** al mes.
   - Ambos planes alcanzaron un uso máximo de **17 a 20 GB**, lo que indica que los patrones de consumo de internet son similares en ambos planes.

##### **4.2 Análisis de Ingresos Mensuales**
- **Plan Surf**:
   - El ingreso promedio mensual de los usuarios de **Surf** fue de **60.13 USD**, con mayor **variabilidad** y **desviación estándar**, lo que indica que los usuarios de Surf tienen patrones de facturación más impredecibles, probablemente debido a la sobrecarga de mensajes o datos.

- **Plan Ultimate**:
   - El ingreso promedio mensual de los usuarios de **Ultimate** fue de **72.28 USD**, con menor **variabilidad** y **desviación estándar**, mostrando un patrón de facturación más consistente y predecible. Los usuarios de Ultimate generalmente se mantienen dentro de sus límites.

##### **4.3 Resultados de las Pruebas de Hipótesis**
- **Hipótesis 1 (Comparación de Ingresos)**: El **ingreso de los usuarios de los planes Surf y Ultimate es significativamente diferente**. Los resultados de la prueba llevaron a rechazar la hipótesis nula, indicando que **los usuarios del plan Ultimate** tienden a tener ingresos mensuales más altos y más consistentes que **los usuarios del plan Surf**.
  
- **Hipótesis 2 (Ingreso por Región)**: **El ingreso de los usuarios en la región NY-NJ no es significativamente diferente** al de los usuarios en otras regiones. Los resultados de la prueba mostraron que no hay diferencias significativas en los ingresos mensuales entre los usuarios de estas dos regiones.

#### **5. Conclusión**

Este análisis de los **planes prepagos de Megaline** revela importantes conocimientos sobre el comportamiento de los clientes:

- **Los usuarios del plan Surf** muestran más variabilidad en sus patrones de uso mensual, especialmente en el uso de mensajes, lo que lleva a ingresos más altos pero más impredecibles.
- **Los usuarios del plan Ultimate** tienen un uso más consistente y menos variabilidad, lo que hace que este plan sea más predecible para Megaline en términos de generación de ingresos.

**Las pruebas de hipótesis** revelaron que el ingreso mensual de los usuarios del **plan Ultimate** es significativamente más alto que el de los usuarios del **plan Surf**. Sin embargo, no se encontraron diferencias significativas en los ingresos entre los usuarios de la región **NY-NJ** y los de otras regiones.

Los hallazgos sugieren que Megaline podría beneficiarse al enfocarse en mejorar la gestión de los clientes de **Surf** para reducir los cargos por excedente y mejorar la previsibilidad de los ingresos. Además, comprender los patrones de ingresos estables de los **usuarios de Ultimate** podría ayudar a prever ingresos futuros.

Este proyecto proporciona información valiosa que puede orientar las estrategias de marketing, precios y mejoras de servicios para los planes prepagos de Megaline.
