# Guía para contribuir

Reglas del equipo para trabajar en este repositorio. `main` está protegida:
**nadie sube directo a `main`**. Todo cambio entra por Pull Request, con
1 aprobación y el pipeline CI en verde.

## Flujo de trabajo

1. **Issue**: crea (o retoma) un issue, asígnatelo, ponle una etiqueta y
   muévelo a **In progress** en el tablero *Práctica DevOps*.
2. **Actualiza `main`** antes de empezar:
   ```bash
   git switch main
   git pull
   ```
3. **Crea tu rama** desde `main` (ver *Nombres de ramas*).
4. **Haz tu cambio** y pruébalo:
   ```bash
   npm run validar
   npm test
   ```
   Abre `index.html` con Live Server para revisarlo.
5. **Commit** siguiendo la convención (ver *Mensajes de commit*).
6. **Publica tu rama** (*Publish Branch*) y revisa que el CI corra en **Actions**.
7. **Abre el Pull Request** hacia `main`:
   - Título con la misma convención que los commits.
   - En la descripción: `Closes #N` (número de tu issue).
   - **Reviewers**: pide revisión a un compañero.
   - **Assignees**: asígnate.
   - Completa la lista de verificación de la plantilla.
8. **Merge**: cuando tenga aprobación y checks en verde, *Merge pull request*
   → *Delete branch*. El issue se cierra solo y el sitio se publica.

## Nombres de ramas

`tipo/descripcion-corta`, en minúsculas y con guiones.

| Tipo        | Uso                                   | Ejemplo                          |
|-------------|---------------------------------------|----------------------------------|
| `feature/`  | Nueva funcionalidad o tarjeta         | `feature/agregar-carlos-ruiz`    |
| `fix/`      | Corrección de un error                | `fix/enlace-github-roto`         |
| `docs/`     | Documentación                         | `docs/agregar-contributing`      |
| `chore/`    | Configuración, pipeline, dependencias | `chore/verificar-ci`             |

## Mensajes de commit

Usamos [Conventional Commits](https://www.conventionalcommits.org/es/):

```
tipo: descripción corta en minúsculas
```

| Tipo       | Cuándo usarlo                                 | Ejemplo                                    |
|------------|-----------------------------------------------|--------------------------------------------|
| `feat`     | Algo nuevo (por ejemplo, una tarjeta)         | `feat: agrega tarjeta de carlos-ruiz`      |
| `fix`      | Corrige un error                              | `fix: corrige usuario de github de Ana`    |
| `docs`     | Solo documentación                            | `docs: agrega guía de contribución`        |
| `style`    | Cambios de CSS o formato, sin lógica          | `style: ajusta colores de las tarjetas`    |
| `test`     | Agrega o modifica pruebas                     | `test: valida nombres con acentos`         |
| `ci`       | Cambios en los workflows de GitHub Actions    | `ci: usa Node 22`                          |
| `chore`    | Mantenimiento, dependencias, configuración    | `chore: actualiza html-validate`           |

## Agregar tu tarjeta

En `js/equipo.js`, escribe tu línea **debajo de tu comentario**
`// --- Integrante N ---` y no modifiques las líneas de los demás:

```js
  // --- Integrante 3 ---
  { nombre: "Carlos Ruiz", rol: "Diseño", github: "carlos-ruiz" },
```

- `nombre`: mínimo 3 caracteres.
- `rol`: obligatorio.
- `github`: tu usuario real, sin `@` ni espacios.
- No olvides la coma al final.

## Revisión de Pull Requests

- No puedes aprobar tu propio PR.
- Para aprobar: *Files changed* → *Review changes* → **Approve** → *Submit review*.
  Un comentario no cuenta como aprobación.
- Si tu rama queda desactualizada o con conflictos, ejecuta en tu rama
  `git pull origin main`, resuelve, haz commit y push.
