# capstone_2026_005D_antismishing SMS Security

**Proyecto Capstone 2026 - Sección 005D**

## Descripción
Aplicación para la detección y prevención de smishing (estafas por SMS) en Chile, con foco en la protección de adultos mayores. El sistema analiza mensajes de texto mediante reglas heurísticas y servicios externos de reputación de dominios, calcula un puntaje de riesgo y ofrece un asistente educativo basado en IA para explicar los resultados.

## Integrantes y Roles
* **Manuel Rivas:** Desarrollador Fullstack
* **Marcel Tusach:** Desarrollador FrontEnd
* **Bryan Acuña:** Jefe de Proyecto

## Tecnologías a utilizar
* **Frontend:** React Native (Android) para la app móvil; React 19 + Vite + Tailwind CSS para el panel de administración web.
* **Backend:** Node.js con Express 5, autenticación JWT, integración con VirusTotal API, RDAP/WHOIS y Google Gemini API.
* **Base de Datos:** MongoDB Atlas (vía Mongoose), con patrón Cache-Aside para optimizar consultas externas.
* **Despliegue:** Backend desplegado en Render (PaaS), con integración continua (CI/CD) desde GitHub. La app móvil se distribuye como APK (sideloading). El panel de administración se ejecuta en entorno local.

## Metodología
El proyecto se desarrolla bajo metodología **Cascada**, dividida en tres fases secuenciales: definición de requerimientos y diseño, desarrollo e integración de componentes, y pruebas/documentación final.

## Arquitectura del Sistema
Diagrama de Arquitectura del Sistema
<img width="1198" height="632" alt="Diagrama Arquitrectura de SMS Security" src="https://github.com/user-attachments/assets/33b3fb04-6fd0-4a22-9590-af5e42c22072" />

Diagrama de Modelo de Base de Datos
<img width="1579" height="918" alt="Modelo de Base de Datos de SMS Security" src="https://github.com/user-attachments/assets/c91ffd4a-227e-4091-af76-2a911a42afb1" />
El sistema sigue un modelo Cliente-Servidor de tres capas: una capa de presentación (app móvil y panel de administración web), una capa de negocio (API REST centralizada en Node.js/Express) y una capa de datos (MongoDB Atlas). El backend se integra de forma asíncrona con servicios externos de reputación de dominios (VirusTotal, RDAP/WHOIS) para el análisis de riesgo, y de forma independiente con Google Gemini para el asistente educativo del chatbot.
