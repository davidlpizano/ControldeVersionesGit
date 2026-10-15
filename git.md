# Introducción y Fundamentos de Git

**Git** es un sistema de control de versiones distribuido (DVCS) de código abierto diseñado para registrar cambios en el código fuente, coordinar el trabajo en equipo y mantener un historial íntegro y trazable de cualquier proyecto.

---

## 1. Los Tres Estados de Git

El flujo local de Git opera a través de tres áreas principales:

```
+------------------+       git add        +------------------+      git commit      +------------------+
| Working Tree     | -------------------> | Staging Area     | -------------------> | Local Repository |
| (Área de trabajo)|                      | (Área de cambio) |                      | (.git / Historial)
+------------------+ <------------------- +------------------+                      +------------------+
                           git checkout / git restore
```

1. **Working Directory (Directorio de trabajo):** Los archivos locales donde trabajas y modificas código directamente.
2. **Staging Area / Index (Área de preparación):** Espacio intermedio donde seleccionas los cambios específicos que formarán el próximo commit.
3. **Repository (Directorio `.git`):** La base de datos local donde quedan guardadas de forma permanente e inmutable las capturas (*snapshots*) del proyecto.

---

## 2. Comandos Esenciales

### Configuración Inicial
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu_correo@ejemplo.com"
```

### Inicialización y Clonado
```bash
git init                  # Inicializa un repositorio local nuevo
git clone <url_repo>      # Clona un repositorio remoto en local
```

### Flujo Básico de Trabajo
```bash
git status                # Muestra el estado del árbol de trabajo y staging
git add <archivo>         # Añade un archivo específico al staging
git add .                 # Añade todos los cambios modificados y creados al staging
git commit -m "Mensaje"   # Registra un commit con un mensaje descriptivo
git log --oneline         # Muestra el historial de commits resumido
```

### Gestión de Ramas
```bash
git branch <nombre_rama>  # Crea una rama nueva
git switch <nombre_rama>  # Cambia a la rama indicada
git switch -c <nueva_rama># Crea y salta a la rama en un solo paso
git merge <rama>          # Fusiona la rama indicada dentro de la rama activa
```

### Sincronización Remota (GitHub / GitLab)
```bash
git remote add origin <url> # Vincula el repositorio local con un servidor remoto
git pull origin <rama>      # Descarga y fusiona los cambios del remoto
git push origin <rama>      # Sube los commits locales al repositorio remoto
```

---

## 3. Buenas Prácticas

- **Commits atómicos:** Cada confirmación debe representar una única unidad lógica o resolución de problema.
- **Mensajes imperativos y claros:** Emplear descripciones concisas (ej. `Añade script de backup`, no `cambios varios`).
- **Uso estricto de `.gitignore`:** Omitir siempre dependencias externas (`node_modules/`, `vendor/`), variables de entorno (`.env`), secretos y temporales del sistema operativo.
