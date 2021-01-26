# WAI-ARIA (_Web Accessibility Initiative_ - _Accessible Rich Internet Applications_)

Con la aparición de la Web 2.0 las páginas web empezaron a utilizar JavaScript en masa y aparecieron cada vez más componentes no estándar, peticiones asíncronas, apareció AJAX... Todo esto complicaba el trabajo de las tecnologías de asistencia impidiendo interpretar las páginas de forma óptima.

## Elementos

Se utilizan los elementos WAI-ARIA para añadir semántica a elementos html utilizados de manera diferente a la intención con la que fueron creados.

### Roles

Identifican zonas de la página ayudando a las tecnologías asistivas a interpretarlas mejor.

Tipos:

- _Abstract roles_.
- _Landmark roles_.
- _Document structure roles_.
- _Widget roles_.
- _Live region roles_.

#### _Landmark roles_

Establecen marcas de navegación para lectores de pantalla e identifican regiones en el documento:

- `banner`.
- `complementary`.
- `contentinfo`.
- `form`.
- `main`.
- `navigation`.
- `region`.
- `search`.

Equivalencias semánticas.

| Rol WAI-ARIA  | Etiqueta HTML5 |
| ------------- | -------------- |
| banner        | header         |
| complementary | aside          |
| contentinfo   | footer         |
| main          | main           |
| navigation    | nav            |

Se recomienda utilizar siempre las etiquetas HTML5.

#### _Document structure roles_

Describen estructuras que organizan el contenido de una página y no suelen ser interactivos.:

- `application`.
- `article`.
- `cell`.
- `columnheader`.
- `definition`.
- `directory`.
- `document`.
- `feed`.
- `figure`.
- `group`.
- `heading`.
- `img`.
- `list`.
- `listitem`.
- `math`.
- `none`.
- `presentation`.
- `region`.
- `row`.
- `rowgroup`.
- `rowheader`.
- `separator`.
- `table`.
- `term`.
- `toolbar`.

Existen dos formas de crear el mismo contenido visual:

- Etiquetas HTML nativas:

```html
<ul>
    <li>Elemento lista 1</li>
    <li>Elemento lista 2</li>
    <li>Elemento lista 3</li>
</ul>
```

- Etiquetas HTML + CSS:

```html
<div class="list">
    <p class="item">Elemento lista 1</p>
    <p class="item">Elemento lista 2</p>
    <p class="item">Elemento lista 3</p>
</div>
```

Sólo se incluyen roles para añadir semántica a las etiquetas que la necesitan:

```html
<div class="list" role="list">
    <p class="item" role="listitem">Elemento lista 1</p>
    <p class="item" role="listitem">Elemento lista 2</p>
    <p class="item" role="listitem">Elemento lista 3</p>
</div>
```

#### _Widget roles_

Un _widget_ es un objeto de la interface con el cual el usuario puede interactuar. Los roles de _widget_ se usan para definir objetos no estándar en HTML:

- Widgets simples:
  - `alert`.
  - `alertdialog`.
  - `button`.
  - `checkbox`.
  - `dialog`.
  - `gridcell`.
  - `link`.
  - `log`.
  - `marquee`.
  - `menuitem`.
  - `menuitemcheckbox`.
  - `menuitemradio`.
  - `option`.
  - `progressbar`.
  - `radio`.
  - `scrollbar`.
  - `searchbox`.
  - `spinbutton`.
  - `status`.
  - `switch`.
  - `tab`.
  - `tabpanel`.
  - `textbox`.
  - `timer`.
  - `tooltip`.
  - `treeitem`.
- Widgets compuestos:
  - `combobox`.
  - `grid`.
  - `listbox`.
  - `menu`.
  - `menubar`.
  - `tablist`.
  - `tree`.
  - `treegrid`.

#### _Live region roles_

Indican que el contenido de la región puede cambiar de forma dinámica sin que el usuario interaccione con ellas.

Roles de widgets que por defecto son regiones activas:

- `alert`.
- `log`.
- `marquee`.
- `status`.
- `timer`.

### Estados y propiedades

#### Atributos de _widgets_

Estados: definen las condiciones actuales de un elemento. Deben ser actualizados con Javascript cuando cambien las condiciones.

- `aria-checked`.
- `aria-disabled`.
- `aria-expanded`.
- `aria-hidden`.
- `aria-invalid`.
- `aria-pressed`.
- `aria-selected`.

Propiedades: proporcionan un significado extra a un elemento.

- `aria-autocomplete`.
- `aria-errormessage`.
- `aria-haspopup`.
- `aria-label`.
- `aria-level`.
- `aria-modal`.
- `aria-multiline`.
- `aria-multiselectable`.
- `aria-orientation`.
- `aria-placeholder`.
- `aria-readonly`.
- `aria-required`.
- `aria-sort`.
- `aria-valuemax`.
- `aria-valuemin`.
- `aria-valuenow`.
- `aria-valuetext`.

#### Atributos de relación

Describen asociaciones entre elementos que no pueden ser directamente deducidas:

- `aria-activedescendant`.
- `aria-colcount`.
- `aria-colindex`.
- `aria-colspan`.
- `aria-controls`.
- `aria-describedby`.
- `aria-details`.
- `aria-errormessage`.
- `aria-flowto`.
- `aria-labelledby`.
- `aria-owns`.
- `aria-posinset`.
- `aria-rowcount`.
- `aria-rowindex`.
- `aria-rowspan`.
- `aria-setsize`.

#### Atributos de regiones activas

Estados:

- `aria-busy`.

Propiedades:

- `aria-atomic`.
- `aria-live [off | polite | assertive]`.
- `aria-relevant [additions | additions text | removals | text | all]`.

## Reglas de uso

- Usar el elemento/atributo nativo de html.
- No cambiar la semántica de los elementos.
- Todos los controles nativos ARIA deben ser usables con el teclado.
