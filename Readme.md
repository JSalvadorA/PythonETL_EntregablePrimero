#### Primer entregable
Este archivo README.md sirve como una guía de referencia rápida para entender el propósito del proyecto, las transformaciones realizadas y cómo reproducir el entorno de trabajo.
A continuación, se describen los pasos clave y las transformaciones realizadas en los datos como parte del proceso.

##### 1. Configuración del Entorno
Se creó un entorno virtual llamado GestionAtenciones con Python 3.11.7.
Se instalaron las dependencias necesarias, incluyendo Polars, xlsx2csv, y otras herramientas complementarias.
##### 2. Carga de Datos
Se importaron múltiples fuentes de datos, incluyendo archivos de texto y hojas de cálculo de Excel.
Los datos importados incluyen información histórica y actual de tickets de atención, así como detalles de atenciones específicas.
#####  3. Transformaciones de Datos
Limpieza de Datos: Se realizaron diversas operaciones de limpieza, incluyendo el tratamiento de valores nulos y la conversión de formatos de datos.
Normalización de Campos: Se reemplazaron valores de texto como "SIN COSTO" y "COSTO CERO" por "0" en la columna Costo Atencion. Además, se reemplazaron las comas por puntos para normalizar los valores numéricos.
Conversión de Datos: Se convirtieron los valores de Costo Atencion a datos decimales, manejando errores de conversión al asignar valores nulos donde fuera necesario.
Transformación de Fechas: Se creó la columna Fecha Real Fin con base en reglas condicionales que dependen de la disponibilidad de datos en Fecha Termino y Fecha Cierre.
Eliminación de Duplicados: Se eliminaron registros duplicados en la base de datos de tickets, asegurando que se mantuvieran los registros con la fecha de creación más reciente.
Segmentación de Datos: Se generó la columna Grupo Dias, clasificando los tickets según la diferencia de días entre la fecha de creación y la fecha de cierre real.
#####  4. Combinación y Consolidación de Datos
Se realizó un Inner Join entre las bases de datos de tickets y atenciones, unificando la información relevante en un único dataframe.
Se exportaron los datos consolidados a un archivo de Excel llamado Consolidado.xlsx, cumpliendo con formatos específicos de fecha y número decimal.

#####  Objetivo del Proyecto
El objetivo principal de este proyecto es demostrar habilidades en el manejo de datos, limpieza y transformación de información, así como la integración de diversas fuentes de datos para generar una base de datos unificada y depurada. Además, se busca asegurar la reproducibilidad del proyecto mediante el uso de entornos virtuales y la documentación adecuada en un repositorio de control de versiones.

Este proyecto se alinea con los requerimientos del curso de Gestión de Atenciones, demostrando competencias técnicas en el uso de herramientas de ETL y la aplicación de buenas prácticas en la manipulación de datos.