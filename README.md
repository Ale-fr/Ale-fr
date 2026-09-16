# ¡Hola! Soy Alejandro Farías 👋
### Desarrollador Full Stack JS Trainee

---

## 📬 Contacto
- **Email:** alejandrofrl02@ejemplo.com 
- **LinkedIn:** [Link al Perfil de LinKedIn](https://linkedin.com/in/alejandro-farias-01b573437) 
- **CV:** 

---

## 🚀 Mis Proyectos (Curso Full Stack - Alkemy)

Mi desarrollo principal se encuentra consolidado en un **único repositorio integrador**, donde evolucionó progresivamente a través de tres módulos:
📌 **[Repositorio Integrador: Proyecto Backend](https://github.com/Ale-fr/Proyecto-backend)**

* **1. Proyecto Módulo 6: Servidor Backend & Lógica de Negocio**  
  * *Descripción:* Estructura inicial del servidor Express, enrutamiento modular, vistas dinámicas con Handlebars y persistencia de logs de peticiones HTTP.  
* **2. Proyecto Módulo 7: Base de Datos & Modelado SQL**  
  * *Descripción:* Integración con Sequelize y MySQL. Modelado de entidades con relaciones 1:N y N:M, operaciones CRUD, búsquedas paginadas y transacciones atómicas con `rollback`.  
* **3. Proyecto Módulo 8: API REST & Autenticación**  
  * *Descripción:* Exposición de una API RESTful segura. Protección de rutas críticas mediante JSON Web Tokens (JWT) y sistema de subida de archivos validados con Multer.  

---

## 📊 Caso de Estudio: Sistema de Gestión de Pedidos con API RESTful y Autenticación JWT

### 📌 1. Descripción de la actividad
Desarrollo de un backend completo para la gestión de usuarios, productos y pedidos. Este proyecto integrador consolida el ciclo completo de desarrollo backend en un único repositorio, evolucionando desde una estructura básica de servidor hasta una API robusta, segura y con persistencia de datos relacional.

### 🎯 2. Desafío principal
Integrar tres capas de complejidad técnica manteniendo la coherencia arquitectónica en un mismo código base: garantizar transacciones atómicas en la creación de pedidos (validación de stock + descuento + registro), implementar autenticación *stateless* con JWT para rutas críticas, y manejar consultas anidadas de relaciones complejas sin afectar el rendimiento.

### 💡 3. Solución propuesta
Se diseñó una **arquitectura modular por capas** (controllers, routes, middlewares, models) dentro del mismo repositorio:
1. **Transaccionalidad:** En `POST /pedidos`, se utilizó `sequelize.transaction()` para envolver todas las operaciones. Si el stock es insuficiente, se lanza un error y Sequelize revierte automáticamente los cambios (*rollback*).
2. **Seguridad:** Se creó un middleware personalizado (`authMidd.js`) que intercepta las peticiones, verifica la firma y expiración del JWT, y asigna los datos del usuario antes de permitir el acceso.
3. **Archivos:** Se configuró Multer con `diskStorage` y un `fileFilter` estricto para aceptar solo imágenes (`jpeg`, `png`, `webp`) con un límite de 2MB, evitando sobrescrituras con nombres únicos basados en timestamp.

### 🛠️ 4. Herramientas técnicas utilizadas
- **Lenguajes / Entorno:** JavaScript / Node.js (v18+)
- **Frameworks:** Express.js
- **Base de Datos:** MySQL (gestionada mediante el ORM Sequelize)
- **Otras herramientas:** Handlebars (hbs), JSON Web Tokens (JWT), Multer, dotenv, Nodemon, Git/GitHub.

### 🎓 5. Principales aprendizajes alcanzados
- Las ventajas del ORM (Sequelize) sobre SQL manual para trabajar con objetos JavaScript, reducir errores sintácticos y prevenir inyecciones SQL.
- La importancia crítica de separar responsabilidades (MVC) desde el inicio para permitir la escalabilidad del proyecto a medida que se agregan módulos.
- Cómo funciona la autenticación *stateless*: el servidor no guarda la sesión, solo valida criptográficamente la firma del token en cada petición.
- La necesidad de las transacciones atómicas para mantener la integridad referencial en operaciones comerciales reales.

### 📈 6. Métricas de impacto logradas
- **Tiempo de resolución:** El sistema completa una transacción de pedido compleja (validación + creación + descuento) en menos de 100ms en entorno local.
- **Eficiencia / Cobertura:** 100% de los endpoints CRUD implementados para las 3 entidades principales, con exclusión automática del campo `pass` en todas las respuestas JSON (usando scopes específicos solo para el login).

### ⚙️ 7. Habilidades técnicas aplicadas
- Diseño de API RESTful con convenciones HTTP y códigos de estado adecuados.
- Modelado de datos con relaciones 1:N y N:M y consultas optimizadas (`include`).
- Implementación y composición de middlewares personalizados (logger, auth, upload).
- Validación y sanitización de datos de entrada y archivos.
- Gestión segura de variables de entorno y control de versiones con Git/GitHub.

### ⭐ 8. Justificación de elección
Elegí este repositorio integrador porque representa mi crecimiento técnico más significativo durante el bootcamp. Demuestra mi capacidad para evolucionar un código base simple hasta convertirlo en una API robusta, aplicando buenas prácticas de la industria (arquitectura modular, seguridad con JWT, integridad de datos con transacciones). Simula un escenario comercial real donde la confiabilidad y el manejo de errores son críticos, preparándome efectivamente para los desafíos de un entorno laboral profesional.
