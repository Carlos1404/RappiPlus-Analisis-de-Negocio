# RappiPlus: análisis de negocio

## Descripción

Proyecto de análisis de datos orientado a evaluar el desempeño del servicio RappiPlus y generar indicadores que apoyen la toma de decisiones. El trabajo integra preparación de datos, análisis de ventas y rentabilidad, funnel de conversión, retención por cohortes y evaluación estadística de un experimento A/B.

## Objetivos

- Revisar la calidad y estructura de los datos.
- Calcular ingresos, costos, inversión en marketing y métricas de compra.
- Analizar el volumen de usuarios en las etapas del funnel.
- Comparar la retención por cohortes mensuales.
- Evaluar la conversión de dos variantes de checkout mediante Chi-cuadrado.
- Organizar los indicadores para su comunicación en un dashboard.

## Herramientas

Python, Pandas, Matplotlib, Seaborn, SQL, PostgreSQL y SQLAlchemy.

## Estructura del proyecto

- `RappiPlus_Analisis_de_Negocio_Portafolio.ipynb`: notebook con el proceso de análisis, consultas, visualizaciones y resultados.

## Principales resultados disponibles

| Indicador | Resultado |
|---|---:|
| Ingreso total | 51,836,375.14 |
| Costo de productos vendidos | 43,078,678.80 |
| Inversión en marketing | 2,694,664.43 |
| Ganancia calculada | 6,063,031.91 |
| Ticket promedio | 2,107.17 |
| Promedio de productos | 7.20 |

- Producto con mayor cantidad vendida: `Laptop-Gaming-16GB`.
- Usuarios únicos en primera visita: 7,796.
- Usuarios únicos con evento de compra: 6,240.
- En el experimento A/B, la conversión observada fue de 15.69 % para control y 16.29 % para tratamiento.
- La prueba Chi-cuadrado obtuvo `p = 0.4319`. Con un nivel de significancia de 0.05, no se encontró evidencia suficiente de una diferencia estadísticamente significativa entre las variantes.

La ganancia calculada se obtiene restando al ingreso el costo de los productos y el gasto de marketing. No debe interpretarse como utilidad neta contable.

## Fuentes de datos

El notebook utiliza archivos CSV publicados en las fuentes de Practicum/TripleTen y tablas PostgreSQL (`events`, `users` y `user_activity`). Las secciones que consultan PostgreSQL requieren acceso autorizado a la base de datos.

## Requisitos

Instala las dependencias con:

```bash
pip install -r requirements.txt
```

## Configuración de PostgreSQL

Por seguridad, las credenciales no están incluidas en el notebook. Antes de ejecutar las secciones de funnel y retención, configura la variable de entorno `DATABASE_URL` con una cadena de conexión válida para tu entorno.

Ejemplo de formato (sustituye los valores por credenciales autorizadas):

```text
postgresql+psycopg2://USUARIO:CONTRASEÑA@HOST:5432/BASE_DE_DATOS
```

En Windows PowerShell, puedes definirla para la sesión actual así:

```powershell
$env:DATABASE_URL = "postgresql+psycopg2://USUARIO:CONTRASEÑA@HOST:5432/BASE_DE_DATOS"
```

No publiques contraseñas, tokens ni archivos `.env` en GitHub.

## Reproducibilidad y alcance

1. Ejecuta las celdas en orden.
2. La carga de los CSV requiere conexión a internet.
3. Las secciones de funnel y retención requieren acceso autorizado a PostgreSQL.
4. Los resultados pueden variar si cambian las fuentes de datos.
5. El dashboard de BI es un entregable independiente y no está incluido en esta versión.

## Nota

Este repositorio presenta un ejercicio de análisis de negocio con fines de portafolio profesional. Las conclusiones se limitan a los datos y métricas disponibles en el proyecto.
