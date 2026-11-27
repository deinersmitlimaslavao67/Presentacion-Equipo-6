# 🚀 Equipo 6 — Análisis y Desarrollo de Software (ADSO)

> **Servicio Nacional de Aprendizaje (SENA)** · Centro de la Industria, la Empresa y los Servicios  
> **Programa:** Tecnólogo en Análisis y Desarrollo de Software (ADSO)  
> **Ficha:** `3407799` · **Instructor:** José de Jesús Motta Vargas

---

## 👋 ¿Quiénes somos?

Somos el **Equipo 6**, un grupo de cinco aprendices del programa **Análisis y Desarrollo de Software (ADSO)** del SENA, enfocados en diseñar y construir soluciones tecnológicas modernas, escalables y orientadas a resolver problemáticas reales de nuestro entorno.

Combinamos habilidades en levantamiento de requisitos, diseño UX/UI, desarrollo web y móvil, arquitectura backend, bases de datos, internacionalización y aseguramiento de calidad (QA), trabajando bajo buenas prácticas de ingeniería de software y metodologías ágiles.

---

## 👥 Integrantes y Roles

| Integrante | Frente de Trabajo / Rol Principal | Enfoque Técnico |
| :--- | :--- | :--- |
| **Cristian Camilo Alegría Rivera** | Coordinación y Análisis de Requisitos | Gestión de alcance, levantamiento de requerimientos (SRS), coordinación de equipo. |
| **Danna Michelle Farfán Ramírez** | Diseño UX/UI y Frontend Web | Wireframes, experiencia de usuario, interfaces responsivas con React, Vite y Tailwind CSS. |
| **Kevin Camilo Caballero Oliveros** | Backend y Seguridad | Arquitectura de APIs REST, WebSockets, autenticación JWT y control de acceso RBAC con NestJS. |
| **Juan Manuel Silva Castañeda** | Desarrollo Móvil y Apoyo QA | Aplicación móvil operativa, soporte *offline-first*, pruebas unitarias, funcionales y de integración. |
| **Deiner Smit Limas Lavao** | Base de Datos, i18n y Documentación | Modelado relacional (PostgreSQL/SQLite), internacionalización (`i18n` / multi-moneda) y documentación técnica. |

---

## 🍽️ Proyecto Formativo Principal: **NexoFood**

**NexoFood** es una **Plataforma Web y Móvil para la Gestión, Centralización e Intermediación Tecnológica del Sector Gastronómico y Restaurantero**.

### 🎯 Propósito
Digitalizar y centralizar la operación de pequeños y medianos restaurantes, reduciendo la dependencia de comisiones elevadas en plataformas agregadoras, eliminando errores de comandas en papel y garantizando la continuidad operativa incluso ante fallas de conectividad a Internet.

### 🧩 Componentes del Ecosistema
1. **Portal Web Administrativo (Backoffice — RF1 a RF5):**
   - Registro y licenciamiento SaaS (planes en `USD`) para establecimientos.
   - Gestión dinámica de roles y permisos de planta (`RBAC`: meseros, cajeros, chefs, domiciliarios propios).
   - Personalización de tienda web con enlace público propio (colores, logo, catálogo y menú dinámico).
   - Gestión de pedidos multicanal (en mesa, para llevar, a domicilio), reservas de mesas, inventario en tiempo real y sucursales multi-sede.
2. **Plataforma Pública / Red Social Gastronómica (RF6):**
   - Exploración abierta de restaurantes y menús sin registro obligatorio para comensales.
   - Sistema de reseñas verificadas y descubrimiento por ubicación.
3. **Aplicación Móvil Operativa (RF7 y RF8):**
   - **Personal de Planta:** Gestión de mesas, inventario y comanda digital en cocina (**KDS**) con arquitectura **Offline-First** (almacenamiento local en SQLite y sincronización diferida automática al recuperar conexión).
   - **Domiciliarios Independientes:** Registro con pase diario de trabajo, acceso a la bolsa de pedidos y rastreo en tiempo real mediante **geolocalización GPS**.
4. **Módulo Transversal de Internacionalización (RF9):**
   - Soporte multilenguaje (`i18n`), manejo de zonas horarias (`UTC`) y liquidación en moneda universal de referencia (`USD`).

---

## 🛠️ Stack Tecnológico y Herramientas

| Categoría | Tecnologías y Herramientas |
| :--- | :--- |
| **Lenguajes** | TypeScript, JavaScript (Node.js 22.x), SQL, Python |
| **Frontend Web** | React.js, Vite, Tailwind CSS (SPA / PWA) |
| **Backend & Tiempo Real** | Node.js, NestJS, API REST, WebSockets, JWT, RBAC |
| **Bases de Datos** | PostgreSQL 16 (central, integridad ACID) · SQLite / Local Storage (modo offline) |
| **Infraestructura & DevOps** | Ubuntu Server 22.04 LTS, Nginx (proxy inverso / balanceo), Docker |
| **Geolocalización y APIs** | Google Maps API / Leaflet |
| **Control de Versiones** | Git + GitHub (flujo colaborativo GitFlow) |
| **Pruebas y Utilidades** | Visual Studio Code, Postman, DBeaver, Jest |
| **Colaboración SENA** | Microsoft 365 (`@soysena.edu.co`: Teams, OneDrive, Outlook, Office Online) |

---

## 🔄 Metodología de Trabajo

Trabajamos bajo el marco ágil **Scrum** con **Sprints de 2 semanas**, lo que nos permite entregar valor de forma incremental y adaptarnos rápidamente a la retroalimentación técnica y académica:

- **Roles:** Product Owner, Scrum Master y Equipo de Desarrollo.
- **Artefactos:** Product Backlog (`HU-01` a `HU-20`), Sprint Backlog e Incrementos funcionales probados.
- **Ceremonias:**
  - *Sprint Planning* para priorizar historias de usuario y tareas técnicas.
  - *Daily Scrum* (15 min) para sincronización diaria y resolución temprana de impedimentos.
  - *Sprint Review* para demostraciones funcionales ante instructores del SENA y partes interesadas.
  - *Sprint Retrospective* para la mejora continua del flujo de trabajo del equipo.

---

## 📚 Entregables y Trabajos Destacados

A lo largo de nuestra etapa de formación en el SENA hemos consolidado diversos entregables técnicos y documentales:

- **Especificación de Requisitos de Software (SRS) — NexoFood:** Levantamiento formal bajo la norma **ISO/IEC/IEEE 29148**, incluyendo 22 requerimientos funcionales específicos (ERF) organizados en 9 módulos (`RF1`–`RF9`), historias de usuario, requerimientos no funcionales, casos de uso y cumplimiento normativo (Ley 1581 de 2012 – Habeas Data).
- **Informe Técnico Consolidado — NexoFood (v1.0):** Documentación integral de arquitectura cliente-servidor desacoplada, evaluación bajo el modelo de calidad **ISO/IEC 25010**, Diagrama Entidad-Relación (**36 tablas en 6 módulos**) con esquema físico, 9 diagramas de actividad, plan de QA, matriz de 10 riesgos técnicos y esquema de licenciamiento.
- **Informe de Análisis y Metodología del Proyecto:** Fundamentación de Scrum, definición de roles, artefactos, ceremonias y trazabilidad de los procesos del sistema.
- **Taller de Identificación y Selección de Software:** Análisis comparativo de lenguajes, frameworks y motores de bases de datos, diagnóstico técnico del entorno de desarrollo del equipo y resolución de caso de estudio aplicado al sector gastronómico.
- **Manual de Herramientas Colaborativas (Microsoft 365):** Guía práctica de adopción y uso del ecosistema colaborativo institucional (`@soysena.edu.co`) para optimizar el trabajo en equipo.

---

## 🤝 Contacto y Colaboración

> ¿Quieres conocer más sobre **NexoFood** o colaborar con el **Equipo 6**?  
> Puedes encontrar nuestros avances, documentación y repositorios en nuestra organización de GitHub y espacios colaborativos del SENA.

---
*Documento elaborado para la presentación oficial del Equipo 6 · ADSO Ficha 3407799 · Neiva - SENA.*