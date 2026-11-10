# Pet Care

Pet Care es un prototipo web estático para que los dueños de mascotas exploren y administren servicios de cuidado animal. La interfaz está construida con HTML y CSS sin frameworks y sigue las pantallas del proyecto en [Figma](https://www.figma.com/design/jhJBHaHnL6MVpbrFzQ4aZO/Untitled?node-id=26-1917&p=f&t=clI8h4zgtEs4h473-0).

## Estructura del proyecto

```text
/
├── index.html                 Página de inicio de sesión y punto de entrada
├── Assets/
│   └── Images/                Fotografías y otros recursos de imagen
├── Pages/                     Las demás páginas HTML
└── Styles/                    Una hoja CSS por cada página HTML
```

### Páginas y sus hojas de estilo

Cada página enlaza directamente su hoja de estilo correspondiente desde el `<head>` del documento. No hay una hoja CSS compartida ni un proceso de compilación.

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

La página de inicio de sesión es `index.html`, en la raíz; las demás páginas están en `Pages/`. La navegación entre páginas se realiza mediante enlaces HTML y acciones de formulario con rutas relativas. Por ejemplo, desde un archivo en `Pages/`, se enlaza otra página de esa carpeta con `./otra-pagina.html`, la raíz con `../index.html` y una hoja de estilo o imagen con `../Styles/...` o `../Assets/Images/...`. La página raíz usa rutas como `./Pages/...` y `./Assets/Images/...`.

## Organización de HTML y CSS

- Los archivos HTML definen el contenido y la estructura de cada página. Se utilizan elementos semánticos como `nav`, `main`, `header`, `section` y `article`, junto con clases que selecciona la hoja de estilo correspondiente.
- Los archivos CSS controlan la presentación y la distribución de cada página. Las páginas del panel usan un diseño flex con una barra lateral a la izquierda y el contenido principal a la derecha; cada pantalla define sus estilos de contenido en `main`.
- Actualmente, las páginas del panel repiten el HTML de la barra lateral y sus reglas CSS en archivos separados. No existe un componente de navegación compartido ni una hoja global. Mantén los cambios limitados a la página solicitada, salvo que se pida explícitamente un cambio compartido, y conserva la barra lateral al modificar únicamente el contenido de una página.
- Cada hoja de estilo tiene sus propias reglas base y de diseño. Por ello, normalmente un cambio en una hoja solo afecta a su página. Al agregar o renombrar clases, revisa y actualiza tanto el marcado como los estilos correspondientes.
- Las imágenes se guardan en `Assets/Images/` y se referencian desde el HTML o CSS con rutas relativas al archivo que las utiliza. Las imágenes de contenido deben tener texto `alt` descriptivo; reserva los fondos CSS para imágenes decorativas.
- El texto de la interfaz está principalmente en español. Conserva el idioma y las convenciones de nombres existentes al agregar contenido.

## Cómo ejecutar el prototipo

Abre `index.html` en un navegador para comenzar en la página de inicio de sesión, o abre directamente una página dentro de `Pages/`. Por el momento, no se necesita instalar paquetes, compilar ni iniciar un servidor.

## Alcance del prototipo

Este repositorio es actualmente un prototipo de interfaz: no cuenta con framework de aplicación, lógica JavaScript, backend ni persistencia de datos. Los formularios y botones pueden navegar entre páginas, pero los controles visuales como buscar, agregar, editar y eliminar no realizan acciones reales, salvo que se implementen explícitamente en la página.
