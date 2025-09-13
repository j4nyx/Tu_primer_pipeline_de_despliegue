# Tu_primer_pipeline_de_despliegue
Evaluación Parcial N°1 Javiera aguirre Elias delgado

#elegimos GitFlow es un concepto:
el cual nos sirvio mas por el echo de que se guia por ciertas ramas, no es tan directo como o trunk-based development, el cual tiene distintas ramas que son mas rectas(llegan mas rapido a un punto, pero saltandose datos importantes a nuestro parecer).
---

```markdown
# Tu primer pipeline de despliegue

Este repositorio implementa un pipeline básico de CI/CD y sigue un conjunto de convenciones para commits, flujos de merge, naming de ramas y revisiones de código.

---

##Convenciones de commits

Se utiliza el estándar **Conventional Commits**:

```

<tipo>(scope): descripción breve

```

**Tipos más usados:**

- `feat`: Nueva funcionalidad  
- `fix`: Corrección de bug  
- `docs`: Documentación  
- `style`: Cambios de formato (espaciado, comillas, etc.)  
- `refactor`: Reestructuración de código sin cambiar funcionalidad  
- `test`: Adición o modificación de pruebas  
- `chore`: Tareas de mantenimiento, configuración o dependencias  

**Ejemplo:**

```

feat(api): agregar endpoint para crear usuarios

```

---

#Naming de ramas

Se utiliza el siguiente patrón:

```

<tipo>/\<número-de-issue>-<descripcion-corta>

```

Ejemplos:

- `feature/12-login-con-google`
- `bugfix/21-error-en-pipeline`
- `hotfix/27-reparar-deploy-produccion`

Esto facilita identificar el objetivo de la rama y relacionarla con un issue o tarea.

---

##Flujo de merge

1. **Crear rama** a partir de `develop` (o `main` si no hay develop).  
2. **Commits pequeños y atómicos**, siguiendo la convención anterior.  
3. **Push** de la rama al repositorio remoto.  
4. **Abrir Pull Request (PR)** hacia `develop`.  
5. Incluir en el PR:
   - Descripción clara del cambio
   - Número de issue relacionado (si aplica)
   - Evidencia (capturas, logs o pruebas)
6. **Revisión por al menos un compañero** antes de hacer merge.  
7. Si todo está correcto:
   - Hacer **merge** usando _Squash & Merge_ (historial limpio) o _Merge Commit_ según corresponda.
   - Borrar la rama después del merge para mantener el repo ordenado.

---

##Estrategias de revisión de código

- **Todo PR debe revisarse** por al menos 1 persona del equipo.  
- La revisión debe validar:
  - Que los commits sigan la convención.
  - Que no haya errores de estilo o código muerto.
  - Que el cambio no rompa el pipeline ni los tests.  
- Si se solicita un cambio, el autor debe actualizar la rama y notificar que está lista para revisar nuevamente.  
- Se recomienda usar linters, formateadores y pruebas automáticas en el pipeline para detectar errores antes de la revisión humana.  

---

## Ejemplo de flujo completo

1. Crear rama `feature/5-agregar-ci`  
2. Hacer commits:  
   - `chore(ci): crear archivo de workflow de github actions`
   - `docs(readme): agregar sección de pipeline`  
3. Hacer push de la rama  
4. Abrir PR y pedir revisión  
5. Ajustar según comentarios  
6. Hacer merge a `develop`  
7. Si es estable, merge a `main` y etiquetar versión (`v1.0.0`)

---

> **Nota:** Estas convenciones pueden evolucionar; este documento debe actualizarse si el equipo acuerda nuevos flujos o estrategias.


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

