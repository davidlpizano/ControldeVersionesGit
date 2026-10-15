# Conceptos Básicos de Git / GitHub

Comprender la diferencia y la relación entre Git (el motor de control de versiones) y GitHub (la plataforma remota de colaboración) es el punto de partida fundamental para cualquier flujo de desarrollo moderno.

---

## 1. Git vs. GitHub: La Distinción Clave

| Aspecto | Git | GitHub |
| :--- | :--- | :--- |
| **Definición** | Software de control de versiones distribuido (CLI / motor). | Plataforma web en la nube basada en Git. |
| **Instalación** | Se instala localmente en tu máquina (Linux, Windows, macOS). | Servicio SaaS al que se accede mediante navegador o API. |
| **Conexión** | Funciona 100% desconectado a internet (*offline*). | Requiere conexión a internet para sincronizar datos. |
| **Función central** | Registrar el historial de cambios, ramas y commits locales. | Alojar repositorios remotos, coordinar equipos y automatizar CI/CD. |

---

## 2. Glosario de Conceptos Fundamentales

### Elementos de Estructura
- **Repositorio (Repo):** Espacio contenedor de un proyecto que almacena los archivos de trabajo y el historial completo de cambios (dentro de la carpeta oculta `.git`).
- **Commit:** Instantánea (*snapshot*) inmutable del estado del proyecto en un momento dado. Cada commit tiene un autor, fecha, mensaje y un identificador criptográfico único (Hash SHA).
- **HEAD:** Puntero interno de Git que indica exactamente en qué commit o rama te encuentras trabajando en este momento.
- **Branch (Rama):** Puntero ligero y móvil hacia un commit concreto. Permite bifurcar el desarrollo para probar ideas o crear funciones sin afectar a la versión principal (`main`).

### Mecanismos de Sincronización
- **Remote:** Alias o enlace simbólico que apunta a la URL del servidor donde reside la copia remota del proyecto (por defecto, `origin`).
- **Fetch:** Descarga los commits, ramas y etiquetas nuevos desde el servidor remoto a tu base de datos local, **sin** aplicar ni fusionar nada en tu código actual.
- **Pull:** Operación compuesta que descarga los cambios remotos y los fusiona de inmediato con la rama local actual (`git pull = git fetch + git merge`).
- **Push:** Envía y publica los commits confirmados en tu repositorio local hacia el repositorio remoto.

---

## 3. Relación entre Espacios: Local vs. Remoto

```
 [ Tu Computadora (Local) ]                   [ Servidor Remoto (GitHub) ]
+----------------------------+               +----------------------------+
|  Working Tree              |               |                            |
|       |   (git add)        |               |                            |
|  Staging Area              |               |                            |
|       |   (git commit)     |               |                            |
|  Local Repository (.git)   |  --- push --> |  Remote Repository         |
|                            |  <-- pull --- |  (origin / main)           |
+----------------------------+               +----------------------------+
```

---

## 4. Conceptos Clave de Colaboración en GitHub

- **Fork:** Duplicado completo de un repositorio ajeno dentro de tu propia cuenta de GitHub, permitiéndote editarlo con permisos totales sin alterar el proyecto original.
- **Pull Request (PR):** Petición formal de revisión para integrar los cambios de una rama (o de un fork) dentro de otra rama de destino. Incluye discusión de código, auditoría de pruebas y aprobación de pares.
- **Issues:** Sistema de tickets integrado para registrar incidencias, tareas planificadas, discusiones técnicas o peticiones de nuevas funciones.

---

## 5. Situaciones Comunes

### Conflictos de Fusión (*Merge Conflicts*)
Ocurren cuando dos ramas han modificado las **mismas líneas** de un mismo archivo y Git no puede determinar automáticamente qué cambio conservar.

Git detiene la fusión y marca el archivo de este modo:
```
<<<<<<< HEAD
Código presente en tu rama actual
=======
Código que proviene de la rama que intentas fusionar
>>>>>>> feature-branch
```
*Solución:* Editar manualmente el archivo eliminando los delimitadores, dejar el código deseado, ejecutar `git add <archivo>` y completar con `git commit`.

### Guardado Temporal (*Stash*)
- **`git stash`:** Almacena temporalmente los cambios modificados que aún no quieres commitear, dejando el árbol de trabajo limpio para cambiar de rama rápidamente.
- **`git stash pop`:** Recupera y vuelve a aplicar los cambios guardados previamente.
