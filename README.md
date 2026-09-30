# ⚽ Mundial 2026 API

API desarrollada como **ejercicio evaluable de control de pipelines**, utilizando una solución .NET y un flujo de integración continua mediante GitHub Actions.

El proyecto está orientado a la creación y validación de una API relacionada con el **Mundial de Fútbol 2026**, incorporando además un proyecto independiente de pruebas y automatización mediante pipelines.

---

## 📋 Descripción

**Mundial2026API** es un proyecto desarrollado para poner en práctica conceptos relacionados con:

* Desarrollo de APIs con .NET.
* Organización de soluciones y proyectos.
* Pruebas automatizadas.
* Integración continua (CI).
* Automatización mediante GitHub Actions.
* Control de calidad del código.
* Ejecución automática de pruebas mediante pipelines.

El repositorio está compuesto por el proyecto principal de la API, un proyecto específico para pruebas y la configuración necesaria para los workflows de GitHub Actions.

---

## 🛠️ Tecnologías utilizadas

* **.NET**
* **C#**
* **ASP.NET Core**
* **Git**
* **GitHub**
* **GitHub Actions**
* **Pruebas automatizadas**

---

## 📁 Estructura del proyecto

La solución está organizada de la siguiente manera:

```text
Mundial2026API/
│
├── .github/
│   └── workflows/
│
├── Mundial2026API/
│
├── Mundial2026API.Tests/
│
├── .gitignore
│
└── Mundial2026API.slnx
```

### `Mundial2026API/`

Contiene el proyecto principal de la aplicación y la implementación de la API.

### `Mundial2026API.Tests/`

Contiene las pruebas automatizadas asociadas al proyecto.

La separación del proyecto principal y el proyecto de pruebas permite mantener una estructura organizada y facilita la ejecución independiente de los tests.

### `.github/workflows/`

Contiene los workflows utilizados para automatizar procesos mediante **GitHub Actions**, especialmente aquellos relacionados con el control del proyecto y sus pipelines.

### `Mundial2026API.slnx`

Archivo de solución utilizado para agrupar los diferentes proyectos que forman parte de la aplicación.

---

# 🔄 Control de pipelines

Uno de los objetivos principales del ejercicio es trabajar con **pipelines de integración continua**.

Los workflows definidos dentro de:

```text
.github/workflows/
```

permiten automatizar diferentes tareas relacionadas con el proyecto.

De esta manera, determinadas comprobaciones pueden ejecutarse automáticamente cuando se realizan cambios en el repositorio.

El flujo general puede representarse como:

```text
        ┌──────────────┐
        │   Git Push   │
        └──────┬───────┘
               │
               ▼
        ┌──────────────┐
        │ GitHub       │
        │ Actions      │
        └──────┬───────┘
               │
               ▼
        ┌──────────────┐
        │ Compilación  │
        └──────┬───────┘
               │
               ▼
        ┌──────────────┐
        │    Tests     │
        └──────┬───────┘
               │
               ▼
        ┌──────────────┐
        │ Resultado    │
        │ del pipeline │
        └──────────────┘
```

---

# 🧪 Pruebas

El repositorio incluye un proyecto independiente:

```text
Mundial2026API.Tests
```

destinado a las pruebas automatizadas de la aplicación.

Estas pruebas permiten comprobar que las funcionalidades desarrolladas continúan funcionando correctamente después de realizar cambios en el código.

La ejecución de las pruebas también puede integrarse dentro del pipeline de GitHub Actions.

---

# 🚀 Instalación

## Requisitos

Para ejecutar el proyecto localmente se necesita disponer de:

* **.NET SDK**
* **Git**
* Un IDE compatible con .NET, como:

  * Visual Studio
  * Visual Studio Code
  * JetBrains Rider

---

## 1. Clonar el repositorio

```bash
git clone https://github.com/P4bM4rx/Mundial2026API.git
```

Acceder al proyecto:

```bash
cd Mundial2026API
```

---

## 2. Restaurar dependencias

Desde la carpeta raíz de la solución:

```bash
dotnet restore
```

Este comando descarga y prepara las dependencias necesarias para los proyectos de la solución.

---

## 3. Compilar el proyecto

```bash
dotnet build
```

Si la compilación finaliza correctamente, el proyecto estará preparado para ejecutar las pruebas o iniciar la aplicación.

---

## 4. Ejecutar las pruebas

Para ejecutar todos los tests de la solución:

```bash
dotnet test
```

Esto permite comprobar localmente el resultado de las pruebas antes de realizar un `push` al repositorio.

---

## 5. Ejecutar la API

Desde el directorio del proyecto principal:

```bash
dotnet run --project Mundial2026API
```

La URL exacta donde estará disponible la API dependerá de la configuración de ejecución del proyecto y del entorno utilizado.

---

# 🔁 Flujo de trabajo recomendado

Un flujo de trabajo habitual para este proyecto sería:

```bash
# Obtener los últimos cambios
git pull

# Realizar modificaciones

# Comprobar que compila
dotnet build

# Ejecutar las pruebas
dotnet test

# Guardar cambios
git add .

git commit -m "Descripción de los cambios"

# Subir los cambios
git push
```

Una vez realizado el `push`, GitHub Actions puede ejecutar automáticamente los procesos definidos en los workflows del repositorio.

---

# ☁️ GitHub Actions

El directorio:

```text
.github/workflows/
```

contiene la configuración de los pipelines del proyecto.

GitHub Actions permite automatizar tareas como:

* Compilación.
* Ejecución de pruebas.
* Comprobaciones del proyecto.
* Validación de cambios.

Esto permite detectar errores de forma automática y comprobar que los cambios realizados no rompen las funcionalidades existentes.

---

# 📊 Arquitectura general

El proyecto se divide principalmente en dos partes:

```text
┌─────────────────────────────────────┐
│          Mundial2026API             │
│                                     │
│      Aplicación / API principal     │
└──────────────────┬──────────────────┘
                   │
                   │ Tests
                   ▼
┌─────────────────────────────────────┐
│        Mundial2026API.Tests         │
│                                     │
│        Pruebas automatizadas        │
└─────────────────────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────┐
│        GitHub Actions               │
│                                     │
│      Automatización / Pipeline      │
└─────────────────────────────────────┘
```

---

# 🎓 Objetivo académico

Este proyecto forma parte de un ejercicio evaluable centrado en el **control de pipelines**.

El desarrollo permite poner en práctica conceptos relacionados con el ciclo de vida del software y la automatización de procesos mediante herramientas de integración continua.

Entre los conocimientos trabajados se encuentran:

* Desarrollo con C# y .NET.
* APIs.
* Tests automatizados.
* Git.
* GitHub.
* Integración continua.
* Pipelines.
* Automatización de tareas.
* Control de cambios.

---

# 🔮 Posibles ampliaciones

El proyecto puede evolucionar incorporando nuevas funcionalidades relacionadas con la gestión del Mundial, así como ampliando la cobertura de pruebas y los procesos automatizados del pipeline.

Algunas posibles líneas de evolución son:

* Ampliar la cobertura de tests.
* Añadir nuevos endpoints.
* Incorporar validaciones adicionales.
* Mejorar el control de errores.
* Añadir análisis de calidad del código.
* Incorporar herramientas de análisis de seguridad.
* Ampliar los workflows de GitHub Actions.
* Automatizar procesos de despliegue.

---

## 👨‍💻 Autor

**Pablo Marchante Fernández**

Proyecto académico — Desarrollo de Aplicaciones Web.

---

## 🔗 Repositorio

Código fuente disponible en GitHub:

[Mundial2026API — GitHub](https://github.com/P4bM4rx/Mundial2026API?utm_source=chatgpt.com)

---

## 📄 Licencia

Proyecto desarrollado con fines académicos.
