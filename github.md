# Repositorios: GitHub

**GitHub** es una plataforma de desarrollo colaborativo basada en la nube que utiliza el sistema de control de versiones Git. Centraliza el alojamiento de repositorios de código, la gestión de proyectos, la revisión colaborativa y la automatización del ciclo de vida del software.

---

## 1. Estructura y Archivos Clave de un Repositorio

Un repositorio bien configurado en GitHub suele incluir archivos estándar en su raíz para estandarizar la colaboración:

- **`README.md`:** Portada y documentación inicial del proyecto. Explica qué hace, cómo instalarlo, dependencias y ejemplos de uso.
- **`.gitignore`:** Lista de patrones de archivos y carpetas que Git debe ignorar permanentemente (claves, logs, carpetas de dependencias o binarios).
- **`LICENSE`:** Define los términos legales bajo los cuales otros pueden usar, modificar o distribuir el código (ej. MIT, Apache 2.0, GPLv3).
- **`CONTRIBUTING.md`:** Guía con normas de estilo, arquitectura y pasos para que colaboradores externos envíen cambios.
- **`.github/`:** Directorio especial para almacenar flujos de trabajo (*workflows* de GitHub Actions) y plantillas de *Issues* y *Pull Requests*.

---

## 2. Flujo de Trabajo Colaborativo (GitHub Flow)

El modelo de colaboración estándar en GitHub se basa en un ciclo iterativo y seguro:

```
    [ main ] -----------------------------------------------> [ main (Actualizado) ]
        \                                                            ^
         \--> [ feature-branch ] --> [ Pull Request / Review ] -----/
```

1. **Crear una rama (*Branch*):** Aislar el desarrollo de una nueva funcionalidad o corrección a partir de `main`.
2. **Realizar cambios y commits:** Trabajar en local y subir los cambios a la rama remota.
3. **Abrir un Pull Request (PR):** Proponer formalmente la integración de los cambios en la rama principal. Abre el espacio para discusión, comentarios de línea por línea y resolución de dudas.
4. **Revisión de código (*Code Review*) y pruebas:** Los revisores evalúan el código y los pipelines automáticos validan que las pruebas pasen sin errores.
5. **Fusión (*Merge*):** Una vez aprobado y verificado, se integra el PR en la rama principal y se elimina la rama secundaria.

---

## 3. Herramientas Integradas del Ecosistema

| Herramienta | Función Principal |
| :--- | :--- |
| **Issues** | Registro, seguimiento y discusión de errores (*bugs*), mejoras o tareas pendientes. |
| **Pull Requests (PR)** |
