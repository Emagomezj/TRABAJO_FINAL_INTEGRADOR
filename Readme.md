# Trabajo Final Integrador - Programación 2
## **Libro - Ficha Bibliográfica**


## Estructura del Repositorio Principal

```
biblioteca-sistema/
├── TIF_API/                 # Backend Spring Boot (API REST)
├── TIF_Consigna/                  # Aplicación de Consola Java
├── README.md               # Este archivo
└── .gitmodules             # Configuración de submodules
└── Informe -Trabajo Integrador Final.pdf
```

## Descripción General

Este trabajo se realiza en el marco de la resolución del Trabajo Integrador Final. Para la misma se realizaron dos proyectos distintos ya que nos pareció interesante desafiarnos a pensar una implementación más cercana a un proyecto real tomando como base lo realizado en el trabajo. <br>
En aras de lograrlo primero realizamos el trabajo tal cual lo pedía la consigna y luego decidimos realizar un backend que funcione como una API REST que nos permitiera simular - someramente - el funcionamiento de una biblioteca real.<br>
Como se ve en el apartado anterior, en el directorio raíz se encuentra el informe del trabajo, el readme que se muestra por pantalla y dos directorios, TIF_API y TIF_Consigna, en los cuales se encuentran el proyecto de desarrollo de una API extendiendo la consigna y el proyecto de la resolución de la consigna  respectivamente.<br>
Cada proyecto también tiene su propio repositorio en caso de que se desee clonar específicamente uno de los dos proyectos a fin de que sea más sencillo el testeo y la corrección. En el mismo encontraran también un Readme con las instrucciones de uso, inicialización y testeo de cada uno.<br>
En el proyecto TIF_API tomamos algunas decisiones a fin de optimizar el proyecto:
- A fin garantizar mayor escalabilidad se decidió que el service no manejaría nada respecto a la conexión a la DB, sino que se delegaría totalmente al DAO, de manera que si luego se necesita cambiar de base de datos o utilizar JPA simplemente se deban modificar los archivos de configuración y el DAO.
- Se elimino ficha bibliográfica, creando una única entidad libro que contenía toda la información del mismo.
- Se agregaron DTOs para el correcto manejo de datos de usuario.


### **TIF_API** - Backend Moderno
**Tecnologías:** Spring Boot 3.5.7, JDBC,MySQL, Mockito, JUnit  
**Arquitectura:** API REST con gestión completa de usuarios, libros y préstamos.

### **TIF_P2** - Aplicación de Consola
**Tecnologías:** Java JDBC, MySQL, Arquitectura por Capas  
**Arquitectura:** Sistema monolítico con interfaz de consola, transacciones ACID y validaciones de negocio.

---

## Características Comparativas

| Característica | TIF_API (Spring Boot)                         | TIF_P2 (Consola JDBC) |
|----------------|-----------------------------------------------|---------------------|
| **Arquitectura** | Monolítica por capas                          | Monolítica por capas |
| **Base de Datos** | MySQL + H2 (tests)                            | MySQL |
| **Autenticación** | No se llevo a cabo pero se contemplo a futuro | No aplica |
| **Transacciones** | Spring Transaction Manager                    | JDBC Manual |
| **Interfaz** | API REST + Postman                            | Consola interactiva |
| **Testing** | JUnit 5 + Mockito                             | Pruebas manuales |
| **Despliegue** | Contenedor Docker                             | Ejecutable local |

---

## Instalación y Configuración

### Prerrequisitos
```bash
  Java 17+
  MySQL 8.0+
  Maven 3.6+
  Git
```

### Clonar el Proyecto Completo
```bash
    git clone https://github.com/Emagomezj/TRABAJO_FINAL_INTEGRADOR
```
---
### Clonar repositorios por separado  
#### TIF_API
```bash
    git clone https://github.com/Emagomezj/tif_p2
```

#### TIF_Consigna
```bash
    git clone https://github.com/Emagomezj/tif_p2_v1
```
---

## Ejecución de los Proyectos

### **TIF_API - Backend Spring Boot**
Primero debe crearse el archivo .env tomando de referencia el .env.example completando los datos.
```bash
cd TIF_API

./mvnw clean install

./mvnw test

./mvnw spring-boot::run

# La API estará en: http://localhost:8080
```

### **TIF_Consigna - Aplicación de Consola**
1. Abrir el proyecto en un IDE (NetBeans o IntelliJ)
2. Antes de correr el proyecto es necesario que se modifiquen los datos de acceso a la base de datos en resources database.properties.
3. Correr AppMenu
## Funcionalidades por Proyecto

### **TIF_API** - Backend Completo
- ✅ CRUD completo de Usuarios, Libros y Préstamos
- ✅ Sistema de roles (ADMIN, USER, LIBRARIAN)
- ✅ Autenticación y seguridad
- ✅ Baja lógica y física
- ✅ Carga masiva de datos
- ✅ Tests unitarios y de integración
- ✅ Documentación API con Postman

### **TIF_Consigna** - Sistema Transaccional
- ✅ Gestión de Libros y Fichas Bibliográficas
- ✅ Transacciones ACID con JDBC
- ✅ Validaciones de negocio
- ✅ Relación 1:1 Libro-FichaBibliografica
- ✅ Baja lógica
- ✅ Búsquedas indexadas

---

## Estructura de Base de Datos

### **TIF_API** - Esquema Avanzado
```sql
-- Usuarios con roles y autenticación
-- Libros con contadores de disponibilidad  
-- Préstamos con estados y fechas
```

### **TIF_P2** - Esquema Transaccional
```sql
-- Libros con información básica
-- Fichas bibliográficas (1:1)
-- Índices para búsquedas eficientes
-- Integridad referencial
```

---

## Testing

### TIF_API
```bash
cd TIF_API
./mvnw test

# Tests unitarios por capa (service, DAO)
# Tests de integración con H2 por Controller
```

### TIF_Consigna
- Pruebas manuales mediante consola
- Validación de transacciones
- Verificación de constraints de BD

---

## Documentación Adicional

### TIF_API
- Readme
- Colección Postman
- Configuración BD
- Scripts SQL
### TIF_Consigna
- Documentación Técnica
- Scripts BD
- Diagrama UML


---

## Autores

### **Equipo de Desarrollo**
- **Matías Farfán**
- **Emanuel Gómez Juárez**
- **Emilia Gómez Juárez**
- **Marianela Guerrero**

### **Institución**
- Universidad Tecnológica Nacional (UTN)
- Tecnicatura Universitaria en Programación

---


### Configuración de Entorno
- Verificar variables de entorno en cada proyecto
- Configurar credenciales de BD según entorno
- Revisar logs de aplicación para troubleshooting

---


