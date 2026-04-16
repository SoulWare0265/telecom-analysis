# 📡 ConnectaTel — Análisis de Uso de Servicios Móviles

## 🏢 Contexto del Proyecto

**ConnectaTel** es una empresa de telecomunicaciones con operaciones en **México y Colombia**. Este proyecto surge de la necesidad de entender cómo los clientes utilizan realmente los servicios móviles (llamadas y mensajes), con el fin de tomar decisiones comerciales más informadas y mejorar la experiencia del usuario.

---

## 🎯 Objetivo

Explorar, limpiar y analizar las bases de datos disponibles para construir una visión **clara, confiable y accionable** sobre el comportamiento de uso de los clientes. En concreto, se busca:

- 🔍 Identificar **patrones de uso** en llamadas y mensajes.
- ⚠️ Detectar **comportamientos atípicos** entre los clientes.
- 👥 Comprender qué **segmentos de clientes** presentan necesidades diferenciadas.
- 💡 Apoyar la **optimización de la oferta comercial** de ConnectaTel.

---

## 📂 Fuentes de Datos

El análisis se basa en tres archivos principales:

| Archivo | Descripción |
|---|---|
| `plans.csv` | Planes disponibles: precio, minutos incluidos, GB incluidos y costo por uso extra. |
| `users_latam.csv` | Información de clientes: edad, ciudad, fecha de registro y plan contratado. |
| `usage.csv` | Detalle de uso real: llamadas (duración) y mensajes (longitud). |

---

## 🗺️ Alcance Geográfico

- 🇲🇽 México  
- 🇨🇴 Colombia

---

## 📌 Análisis Ejecutivo

### ⚠️ Problemas Detectados en los Datos

Los datos presentaban inconsistencias en varias columnas, con valores centinela como `-999`, `999`, `?`, `NA`, `NaN` y espacios en blanco, representando entre el **10% y el 15%** de los registros afectados. En el dataframe de usuarios (`users_latam.csv`), las columnas más impactadas fueron `age`, `reg_date` y `city`. En otros casos, los valores nulos responden a una lógica de negocio válida: clientes que cancelaron su plan no generan registros de duración de llamada ni longitud de mensaje, por lo que esos nulos son esperados y se trataron de forma diferenciada.

---

### 🔍 Segmentos por Edad

Se identificaron tres grupos etarios entre los clientes:

| Segmento | Descripción |
|---|---|
| **Joven** | Usuarios de menor edad, con patrones de uso más orientados a mensajes. |
| **Adulto** | Grupo predominante. Mayor estabilidad económica y uso constante del servicio. |
| **Adulto Mayor** | Menor volumen, con patrones de uso más moderados. |

El segmento **Adulto** es el más representativo de la base de clientes y el de mayor relevancia comercial, dado que utiliza los servicios de forma regular y sostenida.

---

### 📊 Segmentos por Nivel de Uso

Se definieron tres niveles de consumo:

| Nivel | Descripción |
|---|---|
| **Bajo Uso** | Clientes con consumo mínimo de llamadas y mensajes. |
| **Uso Medio** | Segmento masivo, supera los **2,500 usuarios**. Son el motor de la empresa. |
| **Alto Uso** | Clientes de alto consumo individual, candidatos a planes premium. |

El segmento de **Uso Medio**, aunque no es el que más consume individualmente, es el que sostiene el negocio al representar la gran mayoría de la base de clientes.

---

### 🚨 Outliers — ¿Qué Implican?

- **Minutos de llamada elevados:** Se detectaron usuarios con llamadas de hasta **155 minutos**, cuando el usuario típico no supera los 60. Esto indica clientes de alto valor (uso laboral o profesional), pero que sin un plan adecuado pueden generar quejas por cargos extra o, por el contrario, son los candidatos ideales para migrar a un **plan Premium**.

- **Llamadas largas recurrentes:** Duraciones superiores a 60 minutos pueden responder también a contacto con familiares o parejas. Este perfil es un candidato natural para una oferta de **minutos ilimitados**.

---

### 💡 Recomendaciones

**1. Plan "Voz Total" para el segmento Adulto**
Dado que los adultos son el grupo más numeroso y tienen un uso de llamadas consistente, se recomienda diseñar un plan que priorice **minutos ilimitados**. Este segmento prefiere llamar antes que enviar mensajes, por lo que una oferta centrada en voz tendría alta aceptación.

**2. Upgrade automático para clientes de "Alto Uso"**
Los clientes identificados en el segmento de alto consumo deben recibir una **oferta automatizada para el plan Premium**. Al estar rozando los límites de sus planes actuales, representan la oportunidad de conversión más sencilla y rentable para ConnectaTel.

---

## 🛠️ Tecnologías Utilizadas

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter_Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
