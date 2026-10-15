# Lenguaje de Marcas: Markdown

**Markdown** es un lenguaje de marcado ligero creado en 2004 por John Gruber y Aaron Swartz. Su objetivo es permitir la escritura de texto con formato estructurado utilizando una sintaxis de texto plano, intuitiva y legible directamente, convertible de forma nativa a HTML y otros formatos.

---

## 1. Sintaxis Básica

### Encabezados
```markdown
# Encabezado 1 (equivalente a <h1>)
## Encabezado 2 (equivalente a <h2>)
### Encabezado 3 (equivalente a <h3>)
#### Encabezado 4 (equivalente a <h4>)
```

### Formato de Texto
```markdown
**Texto en negrita** o __texto en negrita__
*Texto en cursiva* o _texto en cursiva_
***Negrita y cursiva combinadas***
~~Texto tachado~~
```

### Listas
```markdown
<!-- Lista desordenada -->
- Elemento 1
- Elemento 2
  - Sub-elemento identado (2 o 4 espacios)

<!-- Lista ordenada -->
1. Primer paso
2. Segundo paso
3. Tercer paso
```

### Enlaces e Imágenes
```markdown
[Texto del enlace](https://ejemplo.com "Título opcional")
![Texto alternativo de la imagen](ruta/o/url/imagen.png)
```

### Citas en Bloque
```markdown
> Esto es una cita en bloque.
>> Permite anidación utilizando múltiples símbolos mayor que.
```

---

## 2. Sintaxis Extendida y GitHub Flavored Markdown (GFM)

GitHub utiliza una variante enriquecida (GFM) que añade soporte para tablas, listas de tareas y bloques de código con resaltado de sintaxis.

### Bloques de Código y Sintaxis Resaltada
Para código en línea se utiliza un acento grave simple: `` `variable` ``.

Para bloques completos se utilizan tres acentos graves indicando el lenguaje:
```markdown
```python
def saludar(nombre: str) -> str:
    return f"Hola, {nombre}"
```
```

### Tablas
```markdown
| Herramienta | Tipo       | Estado      |
| :---        | :---:      | ---:        |
| Git         | DVCS       | Activo      |
| Docker      | Contenedor | En ejecución|
```
* `:---` alineación izquierda | `:---:` centrado | `---:` alineación derecha.

### Listas de Tareas (Task Lists)
```markdown
- [x] Configurar repositorio inicial
- [x] Documentar archivo README.md
- [ ] Implementar pipeline CI/CD
```

---

## 3. Separadores y Saltos de Línea

- **Línea horizontal:** Se crea mediante tres o más guiones o asteriscos en una línea vacía (`---` o `***`).
- **Salto de línea suave:** Dos espacios en blanco al final de una línea antes de presionar *Enter*.
- **Salto de párrafo:** Dejar una línea completamente en blanco entre dos bloques de texto.

---

## 4. Buenas Prácticas

- **Consistencia de estilo:** Si usas guiones `-` para listas, mantén guiones en todo el documento en lugar de mezclarlos con asteriscos `*`.
- **Líneas en blanco alrededor de bloques:** Deja siempre una línea vacía antes y después de tablas, listas y bloques de código para evitar errores de renderizado.
- **Uso de `.md`:** Es la extensión estándar recomendada para que editores y plataformas (GitHub, GitLab, Obsidian, VS Code) activen automáticamente el visor y formateador.
