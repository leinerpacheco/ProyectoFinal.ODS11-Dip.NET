# Sistema Inteligente de Reportes Ciudadanos con IA

API REST desarrollada con **ASP.NET Core 8** para la gestión de reportes ciudadanos relacionados con problemáticas urbanas, incorporando **Inteligencia Artificial mediante la API de Groq**, servicios externos de geocodificación y persistencia de información mediante una base de datos relacional.

El sistema está orientado al registro, consulta, actualización, eliminación y análisis inteligente de reportes relacionados con situaciones que afectan la infraestructura y los espacios públicos.

---

## Tabla de contenido

- [Descripción del proyecto](#descripción-del-proyecto)
- [Objetivo](#objetivo)
  - [Objetivo general](#objetivo-general)
  - [Objetivos específicos](#objetivos-específicos)
- [Contexto y ODS 11 – Ciudades y Comunidades Sostenibles](#contexto-y-ods-11--ciudades-y-comunidades-sostenibles)
- [Alcance del proyecto](#alcance-del-proyecto)
- [Características principales](#características-principales)
- [Arquitectura de la solución](#arquitectura-de-la-solución)
- [Tecnologías utilizadas](#tecnologías-utilizadas)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Configuración e instalación](#configuración-e-instalación)
- [Funcionamiento de la API](#funcionamiento-de-la-api)
- [Integración de servicios externos](#integración-de-servicios-externos)
- [Documentación de endpoints](#documentación-de-endpoints)
- [Swagger / OpenAPI](#swagger--openapi)
- [Validaciones y manejo de errores](#validaciones-y-manejo-de-errores)
- [Pruebas y aseguramiento de calidad (QA)](#pruebas-y-aseguramiento-de-calidad-qa)
- [Resultados obtenidos](#resultados-obtenidos)
- [Conclusiones](#conclusiones)
- [Posibles mejoras futuras](#posibles-mejoras-futuras)
- [Autores](#autores)

---

## Descripción del proyecto

### Información general

**Nombre del sistema:** Sistema Inteligente de Reportes Ciudadanos con IA

**Tipo de proyecto:** API REST desarrollada sobre **ASP.NET Core 8**, diseñada bajo una arquitectura orientada a servicios e integrada con tecnologías de Inteligencia Artificial y servicios externos.

El proyecto corresponde al desarrollo de una solución para gestionar reportes ciudadanos relacionados con diferentes problemáticas urbanas.

Su propósito es centralizar la información reportada y facilitar su clasificación y priorización mediante Inteligencia Artificial.

Entre las principales problemáticas que pueden ser registradas se encuentran:

- Baches y deterioro de la malla vial.
- Fallas en el alumbrado público.
- Acumulación de residuos sólidos.
- Daños en parques y zonas verdes.
- Deterioro del mobiliario urbano.
- Afectaciones al espacio público.
- Otras incidencias relacionadas con la infraestructura urbana.

El ciudadano proporciona información como el título del incidente, una descripción detallada y la ubicación donde ocurre el problema.

Una vez registrado el reporte, el sistema almacena la información y utiliza la **API de Groq** para realizar un análisis automático del contenido.

El análisis mediante Inteligencia Artificial permite obtener:

- Categoría del incidente.
- Nivel de prioridad.
- Resumen del problema.
- Recomendación para su atención.

Adicionalmente, el sistema integra una API externa de geocodificación para complementar la información geográfica del reporte.

---

## Objetivo

### Objetivo general

Desarrollar una API REST denominada **Sistema Inteligente de Reportes Ciudadanos con Inteligencia Artificial**, orientada a la gestión eficiente de reportes relacionados con problemáticas urbanas, permitiendo registrar, consultar, actualizar, eliminar y analizar automáticamente la información mediante Inteligencia Artificial.

La solución busca contribuir al mejoramiento de la administración de los espacios públicos y apoyar el cumplimiento del **Objetivo de Desarrollo Sostenible (ODS) 11: Ciudades y Comunidades Sostenibles**.

### Objetivos específicos

#### OE-01. Gestionar reportes ciudadanos

Diseñar e implementar una API REST que permita registrar, consultar, actualizar y eliminar reportes ciudadanos relacionados con problemáticas urbanas.

#### OE-02. Automatizar el análisis de los reportes

Integrar un servicio de Inteligencia Artificial mediante la API de Groq para analizar automáticamente el contenido textual de cada reporte.

#### OE-03. Integrar servicios externos

Consumir una API externa de geocodificación mediante `HttpClient` para complementar la información geográfica asociada a los reportes ciudadanos.

#### OE-04. Garantizar la calidad de la información

Implementar validaciones sobre los datos recibidos mediante DTOs y reglas de negocio.

#### OE-05. Facilitar la consulta y análisis de información

Desarrollar mecanismos de búsqueda y filtrado que permitan consultar reportes por diferentes criterios:

- Categoría.
- Prioridad.
- Estado.
- Rango de fechas.

#### OE-06. Documentar la API

Generar documentación técnica mediante **Swagger/OpenAPI**, describiendo los endpoints disponibles, modelos utilizados, parámetros de entrada, respuestas esperadas y posibles errores.

#### OE-07. Aplicar buenas prácticas de desarrollo

Construir la solución siguiendo principios de separación de responsabilidades, modularidad y escalabilidad.

---

## Contexto y ODS 11 – Ciudades y Comunidades Sostenibles

El proyecto se desarrolla tomando como referencia el **Objetivo de Desarrollo Sostenible (ODS) 11: Ciudades y Comunidades Sostenibles**.

El sistema plantea una solución tecnológica orientada a digitalizar el proceso de registro y administración de problemáticas presentes en el entorno urbano.

### Relación del proyecto con el ODS 11

El proyecto contribuye al ODS 11 mediante una plataforma que centraliza los reportes ciudadanos y permite que estos sean posteriormente analizados y organizados.

La integración de Inteligencia Artificial permite automatizar parte del proceso de clasificación y priorización de los reportes.

### Contribución tecnológica

#### Centralización de la información

La información relacionada con los reportes ciudadanos se almacena en una plataforma centralizada.

#### Automatización mediante Inteligencia Artificial

La integración con la API de Groq permite analizar automáticamente la descripción de cada reporte para identificar:

- Categoría.
- Prioridad.
- Resumen.
- Recomendación.

#### Integración con servicios externos

La API de geocodificación permite complementar la información relacionada con la ubicación de los incidentes.

#### Gestión organizada de la información

El sistema proporciona mecanismos de búsqueda y filtrado para consultar los reportes según diferentes criterios.

---

## Alcance del proyecto

El proyecto comprende el desarrollo de una **API REST** capaz de gestionar integralmente el ciclo de vida de los reportes ciudadanos.

### Funcionalidades incluidas

#### Gestión de reportes

- Registrar nuevos reportes ciudadanos.
- Consultar todos los reportes registrados.
- Consultar un reporte específico mediante su identificador.
- Actualizar la información de un reporte existente.
- Eliminar reportes registrados.
- Consultar reportes utilizando diferentes criterios de búsqueda.

#### Integración con Inteligencia Artificial

La solución integra la API de Groq para realizar el análisis automático del contenido de los reportes.

La Inteligencia Artificial permite:

- Clasificar el tipo de incidente.
- Asignar un nivel de prioridad.
- Generar un resumen.
- Proponer una recomendación.

#### Integración con servicios externos

El sistema consume una API externa de geocodificación mediante `HttpClient`.

#### Persistencia de información

La información se almacena de forma persistente utilizando una base de datos relacional.

#### Consultas y filtros

La API contempla mecanismos de consulta mediante:

- Categoría.
- Prioridad.
- Estado.
- Rango de fechas.

#### Documentación y calidad

El proyecto contempla:

- Documentación mediante Swagger/OpenAPI.
- Validaciones de entrada.
- Manejo de errores.
- Arquitectura modular basada en ASP.NET Core 8.

### Funcionalidades fuera del alcance

La versión inicial no contempla:

- Aplicación móvil.
- Aplicación web para ciudadanos.
- Sistema de autenticación y autorización.
- Panel administrativo gráfico.
- Notificaciones en tiempo real.
- Integración con sistemas gubernamentales reales.

Estas funcionalidades podrán considerarse como mejoras para futuras versiones.

---

## Características principales

| Característica | Descripción |
|---|---|
| API REST | Permite gestionar los reportes mediante servicios HTTP. |
| CRUD de reportes | Registro, consulta, actualización y eliminación de reportes. |
| Inteligencia Artificial | Análisis automático mediante la API de Groq. |
| Clasificación automática | Determinación de la categoría del incidente. |
| Priorización | Asignación automática de un nivel de prioridad. |
| Resumen automático | Generación de un resumen del incidente. |
| Recomendaciones | Generación de recomendaciones para la atención. |
| Geocodificación | Complemento de la información geográfica. |
| Persistencia | Almacenamiento de información en la base de datos. |
| Filtros | Consulta mediante diferentes criterios. |
| Validaciones | Control de los datos recibidos. |
| Swagger/OpenAPI | Documentación y prueba interactiva de la API. |
| Arquitectura modular | Separación de responsabilidades. |

---

## Público objetivo

### Ciudadanos

Personas interesadas en reportar problemáticas relacionadas con la infraestructura urbana de su comunidad.

### Entidades responsables

Organizaciones o dependencias encargadas del mantenimiento y gestión del espacio público, que podrán consultar, analizar y administrar los reportes registrados.

---

## Justificación del proyecto

El crecimiento constante de las ciudades incrementa la necesidad de contar con mecanismos tecnológicos que permitan registrar y administrar de manera organizada las problemáticas presentes en el entorno urbano.

El sistema busca abordar esta problemática mediante una plataforma centralizada que permita registrar y administrar los reportes, complementando el proceso mediante Inteligencia Artificial para automatizar tareas de clasificación y priorización.

Desde el punto de vista académico, el proyecto permite integrar conocimientos relacionados con:

- Desarrollo de APIs REST.
- Arquitectura de software.
- Entity Framework Core.
- Bases de datos.
- DTOs y validaciones.
- Consumo de APIs externas.
- Integración con Inteligencia Artificial.
- Swagger/OpenAPI.
- Buenas prácticas de desarrollo.

---

## Valor agregado del proyecto

El principal valor agregado consiste en la integración de Inteligencia Artificial para interpretar automáticamente la descripción proporcionada por el ciudadano, identificar la naturaleza del problema y asignar una prioridad.

Además, la integración con servicios externos permite enriquecer la información geográfica de los reportes.

# Requerimientos del sistema

## Requerimientos Funcionales y No Funcionales

Los requerimientos del sistema definen las funcionalidades que debe proporcionar la API y las características técnicas y de calidad que debe cumplir la solución.

Se clasifican en:

- **Requerimientos Funcionales (RF):** describen las funciones y servicios que ofrece el sistema.
- **Requerimientos No Funcionales (RNF):** establecen características técnicas, restricciones y criterios de calidad.

---

## Requerimientos Funcionales

Los requerimientos funcionales describen las funcionalidades que debe implementar la API para satisfacer las necesidades de los usuarios y cumplir los objetivos definidos para el proyecto.

| ID | Requerimiento funcional | Prioridad | Estado |
|---|---|---|---|
| FR-01 | El sistema deberá permitir registrar un nuevo reporte ciudadano proporcionando el título, la descripción y la dirección del incidente. | Alta | Planificado |
| FR-02 | El sistema deberá permitir consultar todos los reportes ciudadanos registrados. | Alta | Planificado |
| FR-03 | El sistema deberá permitir consultar un reporte específico mediante su identificador único. | Alta | Planificado |
| FR-04 | El sistema deberá permitir actualizar la información de un reporte existente. | Alta | Planificado |
| FR-05 | El sistema deberá permitir eliminar un reporte previamente registrado. | Alta | Planificado |
| FR-06 | El sistema deberá analizar automáticamente cada reporte mediante la API de Groq una vez sea registrado. | Alta | Planificado |
| FR-07 | El sistema deberá clasificar automáticamente el reporte dentro de una categoría de problemática urbana. | Alta | Planificado |
| FR-08 | El sistema deberá asignar automáticamente un nivel de prioridad al reporte utilizando Inteligencia Artificial. | Alta | Planificado |
| FR-09 | El sistema deberá generar un resumen automático del incidente reportado. | Media | Planificado |
| FR-10 | El sistema deberá generar una recomendación para la atención del incidente utilizando Inteligencia Artificial. | Media | Planificado |
| FR-11 | El sistema deberá almacenar el resultado del análisis realizado por la IA asociado al reporte correspondiente. | Alta | Planificado |
| FR-12 | El sistema deberá consultar el análisis generado para un reporte determinado. | Media | Planificado |
| FR-13 | El sistema deberá permitir consultar reportes filtrando por categoría. | Alta | Planificado |
| FR-14 | El sistema deberá permitir consultar reportes filtrando por estado. | Alta | Planificado |
| FR-15 | El sistema deberá permitir consultar reportes filtrando por prioridad. | Alta | Planificado |
| FR-16 | El sistema deberá permitir consultar reportes mediante un rango de fechas. | Media | Planificado |
| FR-17 | El sistema deberá consumir una API externa de geocodificación para complementar la información geográfica del reporte cuando corresponda. | Media | Planificado |
| FR-18 | El sistema deberá responder las solicitudes mediante servicios REST utilizando formato JSON. | Alta | Planificado |

---

## Requerimientos No Funcionales

Los requerimientos no funcionales establecen las características técnicas y de calidad que debe cumplir el sistema durante su implementación y operación.

| ID | Requerimiento no funcional | Categoría | Estado |
|---|---|---|---|
| RNF-01 | La API deberá desarrollarse utilizando ASP.NET Core 8 y C#. | Plataforma | Planificado |
| RNF-02 | El acceso a la base de datos deberá implementarse mediante Entity Framework Core. | Persistencia | Planificado |
| RNF-03 | La información deberá almacenarse de forma persistente utilizando SQLite durante el desarrollo. | Base de datos | Planificado |
| RNF-04 | La comunicación entre servicios deberá realizarse utilizando el protocolo HTTP y datos en formato JSON. | Interoperabilidad | Planificado |
| RNF-05 | La integración con Groq deberá realizarse mediante HttpClient. | Integración | Planificado |
| RNF-06 | La integración con la API de geocodificación deberá realizarse mediante HttpClient. | Calidad | Planificado |
| RNF-08 | La API deberá documentarse mediante Swagger/OpenAPI. | Documentación | Planificado |
| RNF-09 | El código deberá organizarse siguiendo una arquitectura modular y orientada a servicios. | Arquitectura | Planificado |
| RNF-10 | El sistema deberá implementar DTOs para la transferencia de información entre la API y los consumidores. | Diseño | Planificado |
| RNF-11 | El sistema deberá manejar adecuadamente las excepciones y devolver códigos HTTP apropiados. | Robustez | Planificado |
| RNF-12 | El proyecto deberá mantenerse bajo control de versiones mediante Git y GitHub. | Gestión | Planificado |

> **Nota:** La numeración de los requerimientos se conserva de acuerdo con la documentación original de la Fase 1. Por esta razón, después de `RNF-06` aparece `RNF-08`.

---

# Tecnologías utilizadas

El Sistema Inteligente de Reportes Ciudadanos con IA se desarrolla utilizando tecnologías del ecosistema .NET y servicios externos destinados a construir una API REST modular, mantenible y preparada para integrar capacidades de Inteligencia Artificial.

## Stack tecnológico

| Tecnología | Versión / Tipo | Función |
|---|---|---|
| .NET SDK | 8 LTS | Plataforma de desarrollo y ejecución de la aplicación. |
| C# | 12 | Lenguaje utilizado para implementar la lógica del sistema. |
| ASP.NET Core | 8 | Framework utilizado para desarrollar la API REST. |
| Entity Framework Core | 8 | ORM encargado del acceso y gestión de la base de datos. |
| SQLite | Estable | Base de datos utilizada durante el desarrollo y las pruebas. |
| Groq API | Servicio externo | Procesamiento mediante Inteligencia Artificial. |
| API de Geocodificación | Servicio externo | Obtención y validación de información geográfica. |
| HttpClient | .NET | Consumo de APIs externas. |
| Swagger / OpenAPI | Compatible | Documentación interactiva y pruebas de la API. |
| Git | Control de versiones | Seguimiento de cambios realizados durante el desarrollo. |
| GitHub | Repositorio remoto | Almacenamiento y colaboración sobre el código fuente. |

---

## Descripción de las tecnologías

### .NET 8

Plataforma utilizada como base para el desarrollo y ejecución de la aplicación.

### C# 12

Lenguaje de programación utilizado para implementar los modelos, servicios, controladores, DTOs y demás componentes de la solución.

### ASP.NET Core 8

Framework utilizado para construir la API REST y gestionar las solicitudes HTTP realizadas por los consumidores del sistema.

### Entity Framework Core 8

ORM utilizado para facilitar la comunicación entre la aplicación y la base de datos.

Permite trabajar con los datos mediante objetos de C# y administrar las operaciones de persistencia.

### SQLite

Motor de base de datos utilizado durante el desarrollo y las pruebas para almacenar de forma persistente la información de los reportes y los resultados asociados.

### Groq API

Servicio externo utilizado para incorporar capacidades de Inteligencia Artificial.

El análisis permite obtener información como:

- Categoría.
- Prioridad.
- Resumen.
- Recomendación.

### API de Geocodificación

Servicio externo utilizado para complementar la información geográfica asociada a los reportes ciudadanos.

### HttpClient

Componente de .NET utilizado para realizar solicitudes HTTP hacia los servicios externos integrados con la aplicación.

### Swagger / OpenAPI

Herramienta utilizada para documentar y probar los endpoints de la API de forma interactiva.

### Git y GitHub

Herramientas utilizadas para el control de versiones, seguimiento de cambios y almacenamiento remoto del proyecto.

---

# Integración de servicios externos

La solución contempla la integración con servicios externos para ampliar las capacidades de la API.

Las principales integraciones definidas son:

| Servicio | Propósito | Método de integración |
|---|---|---|
| Groq API | Analizar el contenido de los reportes mediante Inteligencia Artificial. | HttpClient + REST + JSON |
| API de Geocodificación | Validar y complementar la ubicación del reporte. | HttpClient + REST + JSON |

---

## Integración con Groq

La API de Groq permite analizar automáticamente la información textual de los reportes ciudadanos.

### Información enviada

La aplicación proporciona a Groq información relacionada con el reporte, principalmente:

- Título.
- Descripción.

### Información recibida

El análisis generado puede proporcionar:

- Categoría.
- Prioridad.
- Resumen.
- Recomendación.

### Flujo general

```text
Reporte ciudadano
       │
       ▼
API REST
       │
       ▼
Servicio de IA
       │
       ▼
Groq API
       │
       ▼
Análisis del reporte
       │
       ├── Categoría
       ├── Prioridad
       ├── Resumen
       └── Recomendación
       │
       ▼
Persistencia del resultado

## 8.6 Flujo General de Integración

El flujo general de integración describe el proceso que sigue la información desde que el ciudadano registra un reporte hasta que la API devuelve la respuesta correspondiente.

### Flujo del proceso

1. El ciudadano registra un reporte.
2. La API valida la información recibida.
3. Se almacena el reporte en la base de datos.
4. Se consulta la API de Groq para realizar el análisis inteligente.
5. Se consulta la API de geocodificación cuando sea necesario.
6. Se actualiza la información del reporte con los resultados obtenidos.
7. La API devuelve la respuesta al cliente.

### Representación del flujo

```text
Ciudadano
    │
    ▼
Registro del reporte
    │
    ▼
Validación de la información
    │
    ▼
Almacenamiento en la base de datos
    │
    ▼
Análisis mediante API de Groq
    │
    ▼
Geocodificación cuando sea necesaria
    │
    ▼
Actualización de la información
    │
    ▼
Respuesta de la API
    │
    ▼
Cliente
