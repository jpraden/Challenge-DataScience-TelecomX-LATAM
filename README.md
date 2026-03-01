# **Challenge2_TelecomX_LATAM - grupo G9**
**Desarrollado : Jaime Pradenas **
** Diciembre 2025/Enero 2026 **

- Plantilla Trello - https://trello.com/b/KlMd7hug/telecomxlatamjpraden
- Repositorio Github - https://github.com/jpraden/Challenge-DataScience-TelecomX-LATAM/

💡**Acerca del desafío**💡

**Descripción**

Telecom X - Análisis de Evasión de Clientes
Has sido contratado como asistente de análisis de datos en Telecom X y formarás parte del proyecto "Churn de Clientes". La empresa enfrenta una alta tasa de cancelaciones y necesita comprender los factores que llevan a la pérdida de clientes.

Tu desafío será recopilar, procesar y analizar los datos, utilizando Python y sus principales bibliotecas para extraer información valiosa. A partir de tu análisis, el equipo de Data Science podrá avanzar en modelos predictivos y desarrollar estrategias para reducir la evasión.

**¿Qué vas a practicar?**

✅ Importar y manipular datos desde una API de manera eficiente.

✅ Aplicar los conceptos de ETL (Extracción, Transformación y Carga) en la preparación de los datos.

✅ Crear visualizaciones estratégicas para identificar patrones y tendencias.

✅ Realizar un Análisis Exploratorio de Datos (EDA) y generar un informe con insights relevantes.

___________________________________________________________________________________________________________

🛠️ Tecnologías y Herramientas
- Trello 
- Github
- Google Colab - Entorno de desarrollo (Python)
  * Pandas – Manipulación y análisis de datos
  * Matplotlib – Visualización de datos
  * Seaborn – Visualizaciones estadísticas
  * NumPy – Operaciones numéricas

📦 Instalación y Configuración
- Prerrequisitos Python 3.8 o superior
  * pandas>=1.5.0
  * matplotlib>=3.5.0
  * seaborn>=0.12.0
  * numpy>=1.23.0

___________________________________________________________________________________________________________


🛠️ Repositorio del proyecto
- Github --> https://github.com/jpraden/Challenge-DataScience-TelecomX-LATAM/blob/main/TelecomX_LATAM.ipynb

🛠️ Estructura Carpetas en GitHub

../Challenge-DataScience-TelecomX-LATAM

    -> TelecomX_LATAM.ipynb
    -> README.md
    -> TelecomX_Data.json
    -> telecom_churn_data_processed.csv
     ../Graficos
       -> Grafico1_Descriptivos.png
       -> Grafico2_Descriptivo2.png
       -> Grafico3_Descriptivo2.png
       -> Grafico4_Descriptivo2.png
       -> Grafico5_Descriptivo2.png
       
       -> Grafico1_DistribucionChurn.png
       -> Grafico1_DistribucionGenero.png
       -> Grafico1_DistribucionTipoInternet_Churn.png
       -> Grafico1_DistribucionTiempoContrato_Churn.png
       -> Grafico1_DistribucionMetodoPago_Churn.png
       -> Grafico1_DistribucionTipoContratoMetodoPago_Churn.png
       -> Grafico1_DistribucionEtarea_Churn.png
       -> Grafico1_DistribucionPareja_Churn.png
       -> Grafico1_DistribucionSoporteTecnico_Churn.png
       -> Grafico1_DistribucionIntervalo_TasaChurn.png
       -> Grafico1_AbandonoEtapasTempranasChurn.png
       -> Grafico1_TiempoContratoValorMensual.png
       -> Grafico1_RelacionTiemoContratoValorMensual.png
       -> Grafico1_DistribucionGastoToal_Churn.png
 

___________________________________________________________________________________________________________-

🚀 Ejecución del proyecto
- Opción 1: 
  * Abrir cuaderno desde Google Colab (Recomendado)
  * Ejecutar Todo o secuencialmente de nueva casilla

- Opción 2: Jupyter notebook
- Opción 3: Visual Studio Code
** Los gráficos se generarán automáticamente **

___________________________________________________________________________________________________________

📊 #**Actividades realizadas**

✅ Importar y manipular datos desde una API de manera eficiente.

✅ Aplicar los conceptos de ETL (Extracción, Transformación y Carga) en la preparación de los datos.

✅ Realizar un Análisis Exploratorio de Datos (EDA) y generar un informe con insights relevantes.

✅ Crear visualizaciones estratégicas para identificar patrones y tendencias.

#Objetivo:
Identificar patrones y tendencias de abandono a partir de datos de clientes, con el fin de comprender las razones detrás de la evasión y diseñar estrategias de retención más efectivas, tales como:

- Disponibilzar un dataset base para desarrollar modelos predictivos de churn.
- Reducir la tasa de fuga de clientes.
- Apalancar acciones para una mejor satisfacción de clientes con foco a segmentos de alto riesgo.

___________________________________________________________________

#  Pasos aplicados en Extracción, Limpieza y Tratamiento de Datos:

📌 **Extracción**

La fase de extracción es el primer paso en el proceso ETL y consiste en la recopilación de datos desde su fuente original. Para este proyecto, los datos de los clientes de Telecom X fueron obtenidos directamente de una API pública. Esta aproximación garantiza el acceso a la información más reciente y replica un escenario común en el manejo de datos en entornos empresariales.

**1. Fuente de Datos:**
Se utilizó la siguiente URL de API para acceder a los datos de Churn de clientes de Telecom X:

🔗 `https://raw.githubusercontent.com/ingridcristh/challenge2-data-science/refs/heads/main/TelecomX_Data.json`

Mediante la librería `requests` de Python, se realizó una petición GET para obtener el archivo JSON, el cual fue posteriormente cargado en un DataFrame de Pandas. La estructura inicial de este DataFrame mostró un formato anidado, donde varias columnas contenían diccionarios (por ejemplo, `'customer'`, `'phone'`, `'internet'`, `'account'`), lo que requería una posterior normalización para facilitar su análisis.

**2. Extracción e Importación de los datos**

Una vez extraídos, los datos presentaban una estructura anidada, donde algunas columnas contenían diccionarios completos. Para facilitar el análisis y trabajar con una tabla plana, se aplicará la función `pd.json_normalize()` de la librería Pandas. Esta función es esencial para transformar datos JSON o diccionarios anidados en un DataFrame tabular, expandiendo las claves de los diccionarios anidados en nuevas columnas.

Una vez importada la información desde el origen, se deja en un DataFrame, donde se procede a explorar y comprender la data obtenida, los cuales se detallan, a continuación:

**🔍** **Información de la Extracción de datos desde ORIGEN**

  - **filas** - `'7.267'`: Cantidad de registros.
  - **columnas** - `'6'`: Atributos de los datos.

__________________________________________________________________________

Los datos están organizados en un formato jerárquico (diccionario dentro de diccionario), conteniendo la siguiente información:
___________________________________________________________________________

1. **Identificación del Cliente** - `'customerID'`: Identificador único del cliente.
* `'Churn'`: Indica si el cliente canceló el servicio (`Yes` o `No`).

2. **Información del Cliente** (`'customer'`)
* `'gender'`: Género del cliente (`Male` o `Female`).
* `'SeniorCitizen'`: Indica si el cliente es una persona mayor (0 = No, 1 = Sí).
* `'Partner'`: Si el cliente tiene pareja.
* `'Dependents'`: Si el cliente tiene dependientes.
* `'tenure'`: Tiempo de permanencia como cliente (en meses).


3. **Servicios de Telefonía** (`'phone'`)
* `'PhoneService'`: Indica si el cliente posee servicio de teléfono (`Yes` o `No`).
* `'MultipleLines'`: Si posee múltiples líneas telefónicas.


4. **Servicios de Internet** (`'internet'`)
* Tipo de servicio de internet contratado (`DSL`, `Fiber optic`, `No`).
* Servicios adicionales (`OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies`).


5. **Información de la Cuenta** (`'account'`)
* `'Contract'`: Tipo de contrato (`Month-to-month`, `One year`, `Two year`).
* `'PaperlessBilling'`: Si el cliente recibe facturas electrónicas.
* `'PaymentMethod'`: Método de pago (`Bank transfer`, `Credit card`, `Electronic check`, `Mailed check`).
* `'Charges'`:
* `'Monthly'`: Valor mensual cobrado.
* `'Total'`: Valor total pagado por el cliente.

📌 **Transformación**

En esta etapa de tranformación, el foco es realizar los ajustes necesarios de los datos y dejar disponibles para la siguiente etapa de analisis de evasión de clientes de Telecom X.

**Actividades a realizar en esta primera etapa:**

✅ 1. Normalizar el dataset.

✅ 2. Verificar valores ùnicos, nulos, vacíos del dataset normalizado.

✅ 3. Tranformar y corregir las inconsistencias.

✅ 4. Crear la columna de cuentas diarias (Opcional).

✅ 5. Traducir las columnas y/o datos.



_____________________________________________________________________________

**1. Normalizar el dataset.**

*Acción Realizada:*


Se aplicó `pd.json_normalize(data)` al JSON obtenido de la API, lo que resultó en un DataFrame donde las columnas anidadas como `'customer'`, `'phone'`, `'internet'` y `'account'` fueron expandidas en múltiples columnas con nombres que reflejan su jerarquía original (ej. `customer.gender`, `internet.InternetService`, `account.Charges.Monthly`). Este paso es crucial para tener acceso directo a cada atributo y proceder con las siguientes etapas de limpieza y análisis.


**🔍** **Resultados de normalización del dataset**

  - **filas** - `'7.267'`: Cantidad de registros.
  - **columnas** - `'21'`: Atributos de los datos.
_____________________________________________________________________________ 

**2. Verificación de Valores (Únicos, Duplicados, Nulos y Vacíos)**

Antes de cualquier manipulación de datos, es crucial realizar una verificación exhaustiva para identificar y comprender la calidad de los datos. Este proceso incluyó la revisión de valores únicos, duplicados, nulos y vacíos en el DataFrame normalizado.

**Acciones y Hallazgos:**

1.  **Valores Únicos:** Se inspeccionó la cantidad de valores únicos por columna para entender la diversidad de los datos y detectar posibles inconsistencias. Se identificó que columnas como `Churn`, `phone.MultipleLines`, `internet.InternetService`, y otras relacionadas con servicios de internet, tenían categorías como `No phone service` o `No internet service`, lo cual es información útil para el análisis.

2.  **Valores Duplicados:** Se verificó la existencia de filas completamente duplicadas. Afortunadamente, no se encontraron registros duplicados en el conjunto de datos, lo que indica una buena integridad de los datos a nivel de fila.

3.  **Valores Nulos:** Se realizó un recuento de valores nulos (`NaN`). No se encontraron valores nulos iniciales en ninguna columna después de la normalización, lo que facilitó el siguiente paso de la limpieza.

4.  **Valores Vacíos o en Blanco:** Un paso crítico fue la verificación de cadenas de texto vacías o en blanco. Aquí se identificaron dos columnas con problemas:
    *   `Churn`: Se encontraron **224 registros vacíos**, lo que podría sesgar cualquier análisis de la tasa de churn.
    *   `account.Charges.Total`: Se encontraron **11 registros vacíos**, lo cual es problemático para cálculos numéricos.

______________________________________________________________________________


**3. Tranformar y corregir las inconsistencias.**
Identificadas las inconsistencias en las columnas Churn y account.Charges.Total, se procedió a realizar las siguientes acciones para limpiar y preparar el conjunto de datos:

- Conversión de tipo en account.Charges.Total: Se transformó la columna a formato numérico (float), convirtiendo valores no válidos en NaN para facilitar cálculos posteriores.
- Eliminación de registros con Churn vacío: Se descartaron 224 filas sin etiqueta de churn, garantizando consistencia en el análisis.
- Eliminación de registros con account.Charges.Total nulo: Se eliminaron 11 filas con valores faltantes en el total cobrado, evitando distorsiones en métricas financieras.

**Estas correcciones son fundamentales para garantizar la integridad y utilidad del conjunto de datos en las fases posteriores de análisis y modelado.**

________________________________________________________________________________

**4. Creación de nueva columna de "cuentas diarias" en el dataset "df"**

- Acción realizada: Se creó la columna cuentas_diarias dividiendo el valor mensual (valor_mensal) por 30, para estimar el gasto diario promedio de cada cliente.
- Objetivo: Obtener una métrica más granular que permita analizar cómo el costo diario influye en la percepción de valor del servicio y cubrir la actividad **Extra!!.**

- Beneficio: Facilita el estudio del comportamiento de gasto y su relación con el churn, ofreciendo una perspectiva más detallada que el valor mensual.

________________________________________________________________________________

**5. Traducción de Columnas y Datos**

Para mejorar la legibilidad del conjunto de datos y facilitar la interpretación de los resultados en español, se realizó un proceso de traducción tanto de los nombres de las columnas como de los valores dentro de ciertas columnas categóricas.

**Acciones Realizadas:**

1.  **Traducción de Nombres de Columnas:** Se creó un diccionario de mapeo donde las claves eran los nombres originales de las columnas y los valores eran sus equivalentes en español. Luego, se aplicó la función `df.rename(columns=columnas)` para renombrar las columnas del DataFrame. Por ejemplo:
    *   `customer.gender` se convirtió en `genero`
    *   `customer.SeniorCitizen` se convirtió en `tiene +60`
    *   `account.Charges.Monthly` se convirtió en `valor_mensal`
    *   `account.Charges.Total` se convirtió en `total_cobrado`

2.  **Traducción de Valores Categóricos:** Para varias columnas que contenían respuestas categóricas en inglés o términos específicos de servicio, se reemplazaron estos valores por sus equivalentes en español. Esto incluyó:
    *   `Churn`: de 'Yes' a 'Sí'
    *   `genero`: de 'Female' a 'Femenino', 'Male' a 'Masculino'
    *   `posee_pareja` y `posee_dependientes`: de 'Yes' a 'Sí'
    *   `servicio_telefono`: de 'Yes' a 'Sí'
    *   `multiples_lineas`: de 'Yes' a 'Sí', 'No phone service' a 'Sin servicio de teléfono'
    *   `tipo_internet`, `seguridad_online`, `backup_online`, `proteccion_dispositivo`, `soporte_tecnico`, `streaming_tv`, `streaming_peliculas`: de 'No internet service' a 'Sin servicio de internet', y otros valores relevantes.
    *   `tipo_contrato`: de 'One year' a 'Anual', 'Month-to-month' a 'Mensual', 'Two year' a 'Bianual'
    *   `metodo_pago`: se tradujeron los diferentes métodos de pago a español (ej., 'Mailed check' a 'Cheque enviado por correo').

Este proceso de traducción asegura que el DataFrame sea completamente comprensible, facilitando el análisis y la comunicación de los insights.
________________________________________________________________________________

**Aplicados los ajustes y correcciones de traducción de nombres de atributos **

Una vez realizadas las actividades de transformación de limpieza y tratamiento de los datos se obtiene un nuevo DATASET.


**🔍** **Resultados de nuevo dataset ajustado **

  - **filas** - `'7.031'`: Cantidad de registros.
  - **columnas** - `'22'`: Atributos de los datos.

_____________________________________________________________________________

Se ajustan los datos para asegurar que estén completos y coherentes, preparándolos para las siguientes etapas del análisis, donde se ha generado un nuevo dataset con el siguiente diccionario de datos:

**DICCIONARIO DE DATOS -Dataset ajustado con nuevos nombre de atributos traducidos**

1. `'id'`: Identificador único del cliente.
2. `'Churn'`: Indica si el cliente canceló el servicio (`Sí` o `No`).
3. `'genero'`: Género del cliente (`Male` o `Female`).
4. `'tiene +60'`: Indica si el cliente es una persona mayor (0 = No, 1 = Sí).
5. `'posee_pareja'`: Si el cliente tiene pareja (`Sí` o `No`).
6. `'posee_dependientes'`: Si el cliente tiene dependientes (`Sí` o `No`).
7. `'tiempo_contrato'`: Tiempo de permanencia como cliente (en meses).
8. `'servicio_telefono'`: Indica si el cliente posee servicio de teléfono (`Yes` o `No`, `Sin servicio de teléfono`).
9. `'multiples_lineas'`: Si posee múltiples líneas telefónicas. (`Sí` o `No`,  `Sin servicio de teléfono`).
10. `'tipo_internet'`: Servicio de internet (`DSL`, `Fiber optic`, `No`).
11. `'seguridad_online'`: Servicio internet de seguridad (`No`, `Sí`, `Sin servicio de internet'`).
12. `'backup_online '`: Servicio internet de respaldo (`No`, `Sí`, `Sin servicio de internet`).
13. `'proteccion_dispositivo'`: Servicio internet proteciòn (`No`, `Sí`, `Sin servicio de internet`).
14. `'soporte_tecnico'`: Servicio internet soporte tècnico (`No`, `Sí`, `Sin servicio de internet`).
15. `'streaming_tv'`: Servicio internet streaming de televisión (`No`, `Sí`, `Sin servicio de internet`).
16. `'streaming_peliculas'`: Servicio internet streaming de peliculas (`No`, `Yes`, `Sin servicio de internet`).
17. `'tipo_contrato'`: Tipo de contrato (`Mensual`, `Anual`, `Bianual`).
18. `'factura_digital'`: Si el cliente recibe facturas electrónicas (`Sí` o `No`).
19. `'metodo_pago'`: Método de pago (`Transferencia bancaria (automática)`, `Tarjeta de crédito (automático)`, `Cheque enviado por correo`, `Cheque electrónico`).
20. `'valor_mensal'`: Valor mensual cobrado.
21. `'total_cobrado'`: Valor total pagado por el cliente.
22. `'cuentas_diarias'`: Valor cargo en cuenta por día.


_____________________________________________________________________________
_____________________________________________________________________________

**Resumen de las mejoras:**
*   **Extracción:** Los datos fueron obtenidos eficientemente de una API y cargados como un DataFrame de Pandas.
*   **Normalización:** La estructura anidada original fue aplanada utilizando `pd.json_normalize()`, facilitando el acceso a cada atributo.
*   **Limpieza de Valores:** Se gestionaron y eliminaron los registros con valores vacíos en `Churn` (224 registros) y `account.Charges.Total` (11 registros), y se convirtieron los tipos de datos a formatos adecuados.
*   **Creación de Nuevas Características:** Se añadió la columna `cuentas_diarias` para proporcionar un insight más granular sobre el gasto diario del cliente.
*   **Traducción:** Tanto los nombres de las columnas como los valores categóricos clave fueron traducidos al español, mejorando la interpretabilidad y accesibilidad del dataset.

Este proceso asegura que los datos están libres de inconsistencias mayores, listos para ser utilizados en la identificación de patrones y tendencias que contribuyan a comprender y reducir la tasa de Churn en Telecom X.
_____________________________________________________________________________

#📊 Análisis Exploratorio de Datos (gráficos y visualizaciones)

A continuación, se presentan los resultados de los análisis realzidos, los cuales se visualizan en los siguientes gráficos:

       -> Grafico1_RelacionTiemoContratoValorMensual.png
       -> Grafico1_DistribucionGastoToal_Churn.png

![Gráfico1](/Graficos/Grafico1_Descriptivos.png)

![Gráfico2](/Graficos/Grafico2_Descriptivo2.png)

![Gráfico3](/Graficos/Grafico3_Descriptivo2.png)

![Gráfico4](/Graficos/Grafico4_Descriptivo2.png)

![Gráfico5](/Graficos/Grafico5_Descriptivo2.png)

__________________________________________________________________________________________

![Gráfico1](/Graficos/Grafico1_DistribucionChurn.png)

![Gráfico1](/Graficos/Grafico1_DistribucionGenero.png)

![Gráfico1](/Graficos/Grafico1_DistribucionTipoInternet_Churn.png)

![Gráfico1](/Graficos/Grafico1_DistribucionTiempoContrato_Churn.png)

![Gráfico1](/Graficos/Grafico1_DistribucionMetodoPago_Churn.png)

![Gráfico1](/Graficos/Grafico1_DistribucionTipoContratoMetodoPago_Churn.png)

![Gráfico1](/Graficos/Grafico1_DistribucionEtarea_Churn.png)

![Gráfico1](/Graficos/Grafico1_DistribucionPareja_Churn.png)

![Gráfico1](/Graficos/Grafico1_DistribucionSoporteTecnico_Churn.png)

![Gráfico1](/Graficos/Grafico1_DistribucionIntervalo_TasaChurn.png)

![Gráfico1](/Graficos/Grafico1_AbandonoEtapasTempranasChurn.png)

![Gráfico1](/Graficos/Grafico1_TiempoContratoValorMensual.png)

![Gráfico1](/Graficos/Grafico1_RelacionTiemoContratoValorMensual.png)

![Gráfico1](/Graficos/Grafico1_DistribucionGastoToal_Churn.png)

________________________________________________________________________________________________
________________________________________________________________________________________________

**# Resumen ejecutivo de los análisis**
______________________________________________________________________________

**1. Resumen de Resultado de los Descriptvos (Variables Numéricas)**

-  Edad (tiene +60): La mayoría de los clientes no son adultos mayores (83.7%), mientras mayores de 60 años que son 16.2% tienen una tasa de churn significativamente más alta.

- Tiempo de contrato (tiempo_contrato): Promedio de 32.4 meses, mediana de 29 meses, con alta variabilidad (1 a 72 meses). Se observa concentración en clientes nuevos y un segmento leal de larga permanencia.
- Valor mensual (valor_mensal): Promedio de $64.79, mediana de $70.35, con amplia dispersión (entre $18.25 y $118.75), reflejando distintos niveles de servicio.
- Total cobrado (total_cobrado): Promedio de $2283.30, mediana de $1397.47, distribución asimétrica positiva: pocos clientes de larga permanencia elevan el promedio, mientras la mayoría acumula menos gasto.
- Cuentas diarias (cuentas_diarias): Promedio de $2.15, rango más homogéneo (entre $0.60 y $3.95), lo que valida consistencia en la facturación diaria.

_______________________________________________________________________________

**2. Resumen de Resultado de los Descriptvos (Variables Catégoricas)**

1. Churn elevado (26.6%): Uno de cada cuatro clientes abandona el servicio, lo que representa un desafío crítico para la estabilidad y el crecimiento.
2. Género: La tasa de churn es similar entre hombres y mujeres (~26%), sin diferencias significativas.
3. Método de pago:
    - Cheque electrónico: Mayor riesgo de churn (~45.3%).
    - Cheque por correo: Churn moderado (~19.3%).
    - Pagos automáticos: Menor churn (~15–16%), asociados a mayor lealtad.
    - Edad: Los adultos mayores (+60) presentan una tasa de churn mucho más alta (~41.6%) frente a los clientes menores de 60 (~23.6%).
4. Estado civil: Clientes sin pareja muestran mayor propensión al abandono (~32.9%), mientras que los que tienen pareja son más estables (~19.7%).
5. Soporte técnico:
  - Sin soporte: Churn muy alto (~41.6%).
  - Con soporte: Churn bajo (~15.2%), confirmando su rol protector.
  - Sin servicio de internet: Churn mínimo (~7.4%).
6. Tipo de contrato:
  - Mensuales: Mayor tasa de abandono.
  - Anuales y bianuales: Mucho más estables, con churn significativamente menor.

  

**En resumen** Los primeros meses, el tipo de contrato y el método de pago son los principales predictores de churn, fortalecer la experiencia inicial, incentivar contratos largos y pagos automáticos, y garantizar soporte técnico son acciones clave para reducir la fuga y proteger ingresos.


________________________________________________________________________________
________________________________________________________________________________


#📊 Insights claves
Resumen de los principales hallazgos y cómo estos datos pueden ayudar a reducir la evasión 

1. Churn temprano como fenómeno crítico.
    - La mayoría de las fugas ocurren en los primeros meses de contrato, especialmente en clientes con contratos mensuales.
    - Reforzar la experiencia inicial es esencial para reducir la deserción.
2. Factores asociados al churn.
    - Métodos de pago manuales (cheque electrónico o por correo) se relacionan con mayor abandono.
    - Fibra óptica presenta tasas de churn más altas, posiblemente por expectativas no cumplidas o problemas de soporte.
    - Segmentos demográficos vulnerables: adultos mayores (+60) y clientes sin pareja muestran mayor propensión al churn.
3. Indicadores numéricos clave.
    - Tiempo de contrato: correlación negativa fuerte con churn (-0.35).
    - Total cobrado: clientes con menor gasto acumulado son más propensos a abandonar, mientras que los de mayor gasto son más leales.
    - Valor mensual y cuentas diarias: reflejan variabilidad en planes y gasto, útiles para segmentar perfiles de riesgo.
4. Impacto del soporte técnico.
    - Los clientes sin soporte presentan la tasa de churn más alta.
    - El soporte técnico es un factor protector que contribuye a la retención.

#📊Recomendaciones para el equipo de Data Science

1. Modelado predictivo: Incorporar variables como tiempo de contrato, método de pago, tipo de servicio, edad, estado civil y soporte técnico para construir modelos robustos de predicción de churn.

2. Segmentación de riesgo: Identificar grupos vulnerables (contratos mensuales, pagos manuales, fibra óptica, mayores de 60, sin pareja) y diseñar estrategias específicas de retención.

3. Estrategias proactivas:
    - Incentivar contratos más largos y métodos de pago automáticos.
    - Mejorar la experiencia inicial del cliente, especialmente en los primeros 6 meses.
    - Fortalecer el soporte técnico como herramienta de fidelización.

4. Maximización del valor de vida del cliente (CLV): Retener clientes de mayor antigüedad y gasto acumulado, ya que representan la base más estable y rentable.

**En resumen:** El churn en Telecom X, se concentra en etapas tempranas y en segmentos específicos; el equipo de Data Science debe usar estos insights para construir modelos predictivos y guiar estrategias de retención que protejan ingresos y fortalezcan la sostenibilidad del negocio.

______________________________________________________________________________

#📊Conclusión final

El presente informe recopiló, procesó y analizó datos provenientes de la base de clientes, permitiendo identificar factores clave que impulsan el churn y confirmar que este fenómeno afecta directamente los ingresos y el crecimiento sostenido de la empresa. La fuga de clientes en Telecom X, responde a patrones claros vinculados con la experiencia temprana, la estructura contractual y la composición del servicio. Los primeros meses de relación con el cliente se revelan como el período más crítico, especialmente en productos de alto valor como la fibra óptica, donde las expectativas y la calidad del soporte determinan la permanencia.

**En resumen:** Los hallazgos obtenidos constituyen insumos estratégicos para el equipo de Data Science, pueda avanzar en el desarrollo de modelos predictivos y en el diseño de estrategias proactivas de retención.

______________________________________________________________________________

**FINALIZADO / Challenge2_TelecomX_LATAM - Análisis de Evasión de Clientes / Desarrollado por Jaime Pradenas / Grupo G9 DataScience**

______________________________________________________________________________
