---<<<<<<< j4nyx-feature-1
Simulan un desarrollo colaborativo integrando al menos 2 cambios tipo feature y 1 tipo hotfix mediante pull requests.

=======
git checkout develop
git pull origin develop
git checkout -b feature/authentication

#ojala nos vaya bien 
# Tu_primer_pipeline_de_despliegue
Evaluación Parcial N°1 Javiera aguirre Elias delgado

#elegimos GitFlow es un concepto:
el cual nos sirvio mas por el hecho de que se guia por ciertas ramas, no es tan directo como o trunk-based development, el cual tiene distintas ramas que son mas rectas(llegan mas rapido a un punto, pero saltandose datos importantes a nuestro parecer).



#  Ventas API

Este proyecto es un **microservicio REST** desarrollado con **Spring Boot** que permite gestionar **usuarios y ventas**.  
Incluye documentación con **Swagger UI**, conexión a **Oracle Database** y soporte para **HATEOAS**.

---

## Tecnologías utilizadas

- python

---

## Instalación y ejecución

### 1. Clonar el repositorio
```bash
git clone https://github.com/tu-usuario/ventas-api.git
cd ventas-api
```

### 2. Configurar base de datos

Crea una base de datos Oracle (o asegúrate de que exista una instancia).  
Luego ajusta las credenciales en el archivo:

`src/main/resources/application.properties`

```properties
spring.datasource.url=jdbc:oracle:thin:@localhost:1521:XE
spring.datasource.username=usuario
spring.datasource.password=clave
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

**Nota:**  
- Cambia `usuario` y `clave` por tus credenciales reales.  
- También puedes definir variables de entorno para mayor seguridad:
  ```bash
  export DB_USER=usuario
  export DB_PASS=clave
  ```

### 3. Ejecutar la aplicación
```bash
./mvnw spring-boot:run
```

La API estará disponible en:  
 [http://localhost:8080](http://localhost:8080)

Swagger UI:  
 [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)

---

##  Ejemplos de uso

### Crear un usuario
```http
POST /api/usuarios
Content-Type: application/json

{
  "nombre": "Daniel Riquelme",
  "email": "daniel@correo.com"
}
```

### Crear una venta
```http
POST /api/ventas
Content-Type: application/json

{
  "clienteId": 1,
  "monto": 15000
}
```

---

##  Rutas principales de la API

| Método | Endpoint        | Descripción                  |
|--------|-----------------|------------------------------|
| GET    | `/api/usuarios` | Listar usuarios              |
| POST   | `/api/usuarios` | Crear usuario                |
| GET    | `/api/ventas`   | Listar ventas                |
| POST   | `/api/ventas`   | Registrar venta              |

---

## Estructura del proyecto
```
ventas-api/
├── src/
│   ├── main/java/com/miempresa/ventas/
│   │   ├── controller/
│   │   ├── service/
│   │   ├── repository/
│   │   └── model/
│   └── resources/
│       └── application.properties
├── pom.xml
└── README.md
```

---

## Contribuir
¡Las contribuciones son bienvenidas!  
Consulta la guía en [CONTRIBUTING.md](CONTRIBUTING.md).

---

##  Changelog
El historial de cambios está documentado en [CHANGELOG.md](CHANGELOG.md).

---

##  Licencia
Este proyecto está bajo la licencia MIT.  
Consulta el archivo [LICENSE.md](LICENSE.md) para más detalles.
->>>>>>> feature/javiera

#1 feature echo!
