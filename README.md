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
