# 📊 Análisis de Evasión de Clientes - TelecomX LATAM

## ¿De qué trata este proyecto?

Este proyecto es un análisis de datos de una empresa de telecomunicaciones llamada **TelecomX**. Lo que hacemos aquí es investigar por qué los clientes dejan de usar los servicios de la empresa (a esto se le llama **"churn"** o evasión de clientes).

Usamos un archivo con información real de los clientes, y paso a paso vamos limpiando esos datos, organizándolos y creando gráficos para entender mejor qué está pasando. Por ejemplo, podemos ver cosas como:

- ¿Qué tipo de contrato tienen los clientes que se van?
- ¿Influye el método de pago?
- ¿Los clientes nuevos se van más que los antiguos?

Todo el código está escrito en **Python** y se ejecuta dentro de un **notebook** (un archivo `.ipynb`), que es como un cuaderno interactivo donde puedes ir ejecutando el código paso a paso y ver los resultados al instante.

---

## 📁 Archivos del proyecto

| Archivo | ¿Para qué sirve? |
|---|---|
| `TelecomX_LATAM.ipynb` | El notebook principal donde está todo el código del análisis. |
| `TelecomX_Data.json` | El archivo con los datos de los clientes (formato JSON). |
| `TelecomX_diccionario.md` | Una guía que explica qué significa cada columna de los datos. |
| `README.md` | Este archivo que estás leyendo ahora mismo 😄. |

---

## 🛠️ ¿Qué necesitas tener instalado?

### Opción 1: Usar Google Colab (la más fácil, no necesitas instalar nada)

Si no quieres complicarte instalando cosas en tu computadora, puedes usar **Google Colab**, que es una herramienta gratuita de Google que te permite ejecutar notebooks directamente en tu navegador.

Solo necesitas:
1. Una cuenta de Google (la misma de Gmail sirve).
2. Subir el archivo `TelecomX_LATAM.ipynb` a Google Colab.

> 💡 **Dato:** El notebook ya descarga los datos directamente desde internet, así que no necesitas tener el archivo JSON en tu computadora si usas esta opción.

### Opción 2: Ejecutar en tu computadora

Si prefieres trabajar en tu propia computadora, necesitas tener instalado lo siguiente:

#### 1. Python (versión 3.8 o superior)

Python es el lenguaje de programación que usamos. Puedes descargarlo desde [python.org](https://www.python.org/downloads/).

> ⚠️ **Importante:** Al instalar Python en Windows, asegúrate de marcar la casilla que dice **"Add Python to PATH"** antes de hacer clic en "Install Now".

#### 2. Jupyter Notebook

Jupyter es la herramienta que nos permite abrir y ejecutar los archivos `.ipynb`. Se instala fácilmente con un solo comando.

Abre tu **terminal** (o **Símbolo del sistema** en Windows / **Terminal** en Mac/Linux) y escribe:

```bash
pip install jupyter
```

#### 3. Las librerías de Python que usa el proyecto

El notebook usa las siguientes librerías:

- **pandas** → Para leer, organizar y manipular los datos (piensa en ella como unas tablas de Excel muy poderosas).
- **matplotlib** → Para crear los gráficos y visualizaciones.

Para instalar ambas, ejecuta este comando en tu terminal:

```bash
pip install pandas matplotlib
```

> 💡 Si alguna de estas ya está instalada en tu computadora, no te preocupes, el comando simplemente la saltará.

---

## 🚀 ¿Cómo ejecutar el proyecto?

### Si usas Google Colab:

1. Ve a [colab.research.google.com](https://colab.research.google.com/).
2. Haz clic en **"Subir"** (o "Upload").
3. Selecciona el archivo `TelecomX_LATAM.ipynb` desde tu computadora.
4. Una vez abierto, puedes ejecutar cada celda (bloque de código) haciendo clic en el botón de **▶ (play)** que aparece a la izquierda de cada una, o presionando **Shift + Enter** en tu teclado.

### Si usas Jupyter Notebook en tu computadora:

1. Abre tu terminal.
2. Navega hasta la carpeta donde descargaste el proyecto. Por ejemplo:
   ```bash
   cd ruta/de/la/carpeta/challenge2-data-science-LATAM
   ```
3. Inicia Jupyter Notebook con este comando:
   ```bash
   jupyter notebook
   ```
4. Se abrirá una ventana en tu navegador con los archivos del proyecto. Haz clic en **`TelecomX_LATAM.ipynb`** para abrirlo.
5. Ejecuta cada celda en orden, de arriba hacia abajo, haciendo clic en **▶ (Run)** o presionando **Shift + Enter**.

---

## 📖 ¿Qué hace el notebook paso a paso?

El análisis está dividido en secciones para que sea fácil de seguir:

### 📌 1. Extracción
En esta parte descargamos los datos desde internet. El archivo es un JSON (un formato muy común para guardar información) que contiene datos de más de **7,000 clientes**.

### 🔧 2. Transformación
Aquí es donde "arreglamos" los datos para que sean más fáciles de analizar:
- **Desanidamos columnas:** Los datos originales vienen con información agrupada (como los datos del cliente, del teléfono, del internet, etc.), así que los separamos para tener una tabla más clara.
- **Revisamos valores faltantes:** Nos aseguramos de que no haya datos vacíos que puedan causar problemas.
- **Corregimos tipos de datos:** Por ejemplo, si un número estaba guardado como texto, lo convertimos a número.
- **Eliminamos duplicados:** Quitamos filas repetidas para no contar dos veces al mismo cliente.
- **Creamos una nueva columna:** Calculamos cuánto paga cada cliente por día (`Cuentas_Diarias`), dividiendo el cobro mensual entre 30.
- **Convertimos valores:** Cambiamos los "Yes/No" por 1/0 para poder hacer cálculos más fácilmente.

### 📊 3. Carga y Análisis
En esta sección exploramos los datos ya limpios:
- **Estadísticas generales:** Media, mediana y desviación estándar de las variables numéricas.
- **Distribución del churn:** ¿Cuántos clientes se fueron vs. cuántos se quedaron?
- **Análisis por categorías:** Creamos gráficos para ver cómo influyen factores como:
  - El **género** del cliente.
  - El **tipo de contrato** (mensual, anual, etc.).
  - El **método de pago**.
  - Los **cargos mensuales y totales**.

---

## 📊 Diccionario de datos

Para que entiendas qué significa cada columna en los datos:

| Columna | Descripción |
|---|---|
| `customerID` | Número de identificación único de cada cliente. |
| `Churn` | Si el cliente dejó o no la empresa (1 = sí, 0 = no). |
| `gender` | Género (masculino o femenino). |
| `SeniorCitizen` | Si el cliente tiene 65 años o más (1 = sí, 0 = no). |
| `Partner` | Si el cliente tiene pareja. |
| `Dependents` | Si el cliente tiene dependientes. |
| `tenure` | Meses de contrato del cliente. |
| `PhoneService` | Si tiene servicio telefónico. |
| `MultipleLines` | Si tiene más de una línea telefónica. |
| `InternetService` | Tipo de servicio de internet (DSL, Fibra óptica, o ninguno). |
| `OnlineSecurity` | Si tiene seguridad en línea. |
| `OnlineBackup` | Si tiene respaldo en línea. |
| `DeviceProtection` | Si tiene protección del dispositivo. |
| `TechSupport` | Si tiene soporte técnico. |
| `StreamingTV` | Si tiene televisión por cable. |
| `StreamingMovies` | Si tiene streaming de películas. |
| `Contract` | Tipo de contrato (mensual, un año, dos años). |
| `PaperlessBilling` | Si prefiere factura en línea. |
| `PaymentMethod` | Forma de pago. |
| `Charges.Monthly` | Total que paga el cliente por mes. |
| `Charges.Total` | Total que ha gastado el cliente. |
| `Cuentas_Diarias` | Cobro diario estimado (columna creada en el análisis). |

---

## 💡 Consejos útiles

- **Ejecuta las celdas en orden:** El código de cada sección depende de los anteriores, así que es importante seguir el orden de arriba hacia abajo.
- **No te asustes si ves errores:** A veces al ejecutar una celda puede aparecer un aviso (warning), eso generalmente no es un problema grave. Lo importante es que no aparezcan errores en rojo.
- **Experimenta:** Una vez que ejecutes todo el notebook, puedes volver a cualquier celda, cambiar cosas y volver a ejecutar para ver qué pasa. ¡Así es como se aprende!

---

## 🤝 ¿Quieres contribuir?

Si tienes ideas para mejorar el análisis o encontraste algún error, puedes:

1. Hacer un **fork** de este repositorio.
2. Crear una **rama** con tus cambios.
3. Enviar un **pull request** para que revisemos tus mejoras.

---

*Este proyecto fue desarrollado como parte del Challenge de Data Science de [Alura LATAM](https://www.aluracursos.com/).*
