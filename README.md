# Tarea3--Procesamiento--Batch
# Tarea 3 – Procesamiento de Datos con Apache Spark

## Descripción

Este proyecto desarrolla el procesamiento de datos por lotes (Batch) utilizando Apache Spark y PySpark.

Se trabaja con el conjunto de datos histórico de la Tasa Representativa del Mercado (TRM), almacenado en HDFS. El procesamiento permite consultar la información, identificar su estructura, obtener estadísticas descriptivas y filtrar los registros cuyo valor sea superior a 5000.

## Tecnologías utilizadas

- Apache Hadoop 3.3.6 (HDFS).
- Apache Spark 3.5.8.
- Python.
- PySpark.
- Ubuntu Server 22.04.

## Estructura del proyecto

- `tarea3.py`: código fuente del procesamiento Batch.
- `rows.csv`: conjunto de datos utilizado (si se incluye en el repositorio).

## Requisitos

- Java 11.
- Apache Hadoop configurado y con HDFS en funcionamiento.
- Apache Spark instalado.
- Python y PySpark disponibles.

## Instrucciones de ejecución

**1. Iniciar los servicios de Hadoop**

Iniciar HDFS y comprobar que sus servicios estén activos.

**2. Cargar el conjunto de datos en HDFS**

Si se incluye el archivo `rows.csv` en el repositorio, cargarlo utilizando:

```bash
hdfs dfs -mkdir -p /Tarea3
hdfs dfs -put -f rows.csv /Tarea3/rows.csv
```

**3. Ejecutar el procesamiento**

Desde el directorio donde se encuentra `tarea3.py`, ejecutar:

```bash
spark-submit tarea3.py
```

El programa lee los datos desde:

`hdfs://localhost:9000/Tarea3/rows.csv`

## Operaciones realizadas

1. Lectura del conjunto de datos desde HDFS.
2. Identificación del esquema y visualización de registros.
3. Generación de estadísticas descriptivas.
4. Filtrado de registros con valores superiores a 5000.
5. Ordenamiento de los resultados de mayor a menor.

## Resultados

El conjunto de datos procesado contiene 8.378 registros. Se obtiene un promedio aproximado de 2.373,67 y un valor máximo de 5.061,21.

Los resultados permiten observar el comportamiento de los valores históricos de la TRM mediante las operaciones de procesamiento Batch de Apache Spark.
