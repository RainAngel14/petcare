# Pet Care

Pet Care es un prototipo web estático para que los dueños de mascotas exploren y administren servicios de cuidado animal. La interfaz está construida con HTML y CSS sin frameworks y sigue las pantallas del proyecto en [Figma](https://www.figma.com/design/jhJBHaHnL6MVpbrFzQ4aZO/Untitled?node-id=26-1917&p=f&t=clI8h4zgtEs4h473-0).

## Estructura del proyecto

```text
/
├── index.html                 Página de inicio de sesión y punto de entrada
├── Assets/
│   └── Images/                Fotografías y otros recursos de imagen
├── Pages/                     Las demás páginas HTML
└── Styles/                    Hojas CSS por página y estilos compartidos
```

### Páginas y sus hojas de estilo

Cada página enlaza su hoja de estilo desde el `<head>` del documento. Las páginas con navegación lateral cargan además `Styles/shared-layout.css`, después de su hoja individual, para mantener uniforme la navegación y el resumen de cuenta. No hay un proceso de compilación.

| Página | HTML | Hoja de estilo |
|---|---|---|
| Inicio de sesión | `index.html` | `Styles/index.css` |
| Registro | `Pages/register.html` | `Styles/register.css` |
| Panel principal | `Pages/initial-panel.html` | `Styles/initial-panel.css` |
| Explorar servicios | `Pages/explore-services.html` | `Styles/explore-services.css` |
| Mis mascotas | `Pages/my-pets.html` | `Styles/my-pets.css` |
| Mis reservas | `Pages/my-reserves.html` | `Styles/my-reserves.css` |
| Detalle de la reserva | `Pages/reserve-details.html` | `Styles/reserve-details.css` |
| Mi perfil | `Pages/my-profile.html` | `Styles/my-profile.css` |
| Estilos compartidos del panel | — | `Styles/shared-layout.css` |

La página de inicio de sesión es `index.html`, en la raíz; las demás páginas están en `Pages/`. La navegación entre páginas se realiza mediante enlaces HTML y acciones de formulario con rutas relativas. Por ejemplo, desde un archivo en `Pages/`, se enlaza otra página de esa carpeta con `./otra-pagina.html`, la raíz con `../index.html` y una hoja de estilo o imagen con `../Styles/...` o `../Assets/Images/...`. La página raíz usa rutas como `./Pages/...` y `./Assets/Images/...`.

## Organización de HTML y CSS

- Los archivos HTML definen el contenido y la estructura de cada página. Se utilizan elementos semánticos como `nav`, `main`, `header`, `section` y `article`, junto con clases que selecciona la hoja de estilo correspondiente.
- Las hojas CSS individuales controlan el contenido y la distribución propia de cada pantalla. `Styles/shared-layout.css` establece las dimensiones, los estados y el comportamiento responsive comunes de la barra lateral, del enlace activo, del cierre de sesión y de las tarjetas de cuenta. Se carga después del CSS individual para que estas reglas sean consistentes.
- El HTML de la navegación sigue repetido en las páginas del panel; al modificar sus enlaces o etiquetas, aplica el mismo cambio a todas. Conserva la clase `active` únicamente en la sección actual. Las páginas `index.html` y `Pages/register.html` no incluyen navegación lateral ni tarjeta de cuenta.
- En escritorio, el menú lateral se mantiene como columna; hasta 700 px pasa a una franja superior con navegación horizontal desplazable. La tarjeta de cuenta mantiene el mismo tamaño en todas las páginas y compacta el texto en pantallas estrechas.
- El panel principal también reorganiza sus servicios y tarjetas de proveedores en columnas adaptables en pantallas estrechas.
- `index.html` y `Pages/register.html` tienen CSS independiente y diseños apilados para móvil, sin depender de la hoja de estilos compartida.
- Cada hoja de estilo tiene sus propias reglas base y de diseño. Por ello, normalmente un cambio en una hoja solo afecta a su página. Al agregar o renombrar clases, revisa y actualiza tanto el marcado como los estilos correspondientes.
- Las imágenes se guardan en `Assets/Images/` y se referencian desde el HTML o CSS con rutas relativas al archivo que las utiliza. Las imágenes de contenido deben tener texto `alt` descriptivo; reserva los fondos CSS para imágenes decorativas.
- El texto de la interfaz está principalmente en español. Conserva el idioma y las convenciones de nombres existentes al agregar contenido.

## Cómo ejecutar el prototipo

Abre `index.html` en un navegador para comenzar en la página de inicio de sesión, o abre directamente una página dentro de `Pages/`. Por el momento, no se necesita instalar paquetes, compilar ni iniciar un servidor.

## Alcance del prototipo

Este repositorio es actualmente un prototipo de interfaz: no cuenta con framework de aplicación, lógica JavaScript, backend ni persistencia de datos. Los formularios y botones pueden navegar entre páginas, pero los controles visuales como buscar, agregar, editar y eliminar no realizan acciones reales, salvo que se implementen explícitamente en la página.
