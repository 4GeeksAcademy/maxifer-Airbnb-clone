# Contexto del proyecto

## Nombre del proyecto

Clon de interfaz de Airbnb con Next.js y React.

## Objetivo

El objetivo de este proyecto es construir una réplica visual y funcional de tres vistas principales de una experiencia tipo Airbnb:

1. Página de inicio.
2. Página de catálogo o resultados de búsqueda.
3. Página de detalle de una habitación o alojamiento.

El foco está en practicar arquitectura de componentes, diseño mobile-first, navegación entre páginas y construcción de interfaces modernas usando Next.js, React, TypeScript y Tailwind CSS.

## Usuario objetivo

El usuario es una persona que busca un alojamiento temporal para viajar, descansar o trabajar desde otro lugar. Quiere explorar opciones de hospedaje, comparar precios, revisar información básica y entrar al detalle de una propiedad que le interese.

## Experiencia principal

El usuario debe poder:

* Ver una página inicial atractiva con barra de búsqueda, categorías y alojamientos destacados.
* Navegar hacia una página de resultados con una lista de alojamientos disponibles.
* Seleccionar un alojamiento y ver una página de detalle con imágenes, descripción, precio, ubicación, servicios y datos del anfitrión.
* Moverse entre las páginas sin recargar el navegador, usando la navegación propia de Next.js.

## Enfoque de diseño

La implementación será mobile-first. Primero se diseñará para un viewport de 375px y luego se adaptará a escritorio desde 768px.

La interfaz debe sentirse limpia, moderna y visual, tomando como referencia la experiencia de Airbnb: tarjetas con imágenes grandes, bordes redondeados, buena separación entre elementos, textos claros y jerarquía visual marcada.

## Páginas principales

### Home

La página de inicio debe presentar una experiencia simple para comenzar una búsqueda.

Componentes principales:

* Header o barra superior.
* Barra de búsqueda.
* Categorías de alojamientos.
* Sección de alojamientos destacados.
* Tarjetas de alojamiento.
* Navegación inferior en mobile si aplica.

La intención de esta vista es que el usuario pueda descubrir alojamientos rápidamente y acceder al catálogo.

### Catálogo / Resultados de búsqueda

La página de catálogo muestra una lista de alojamientos disponibles.

Componentes principales:

* Header compacto.
* Filtros o chips de categorías.
* Lista o grilla de propiedades.
* Tarjetas con imagen, ubicación, descripción breve, rating y precio.
* Link hacia la página de detalle.

La intención de esta vista es permitir que el usuario compare opciones antes de elegir una.

### Detalle de habitación

La página de detalle muestra información completa de un alojamiento seleccionado.

Componentes principales:

* Galería de imágenes.
* Título del alojamiento.
* Ubicación.
* Rating y cantidad de reseñas.
* Información del anfitrión.
* Descripción.
* Lista de servicios.
* Caja de reserva con precio por noche.
* Botón principal de reserva.
* Navegación para volver al catálogo.

La intención de esta vista es que el usuario evalúe si ese alojamiento es adecuado para su viaje.

## Componentes reutilizables

La aplicación debe estar organizada con componentes pequeños y enfocados. Algunos componentes posibles son:

* `Header`
* `SearchBar`
* `CategoryList`
* `CategoryChip`
* `PropertyCard`
* `PropertyGrid`
* `ImageGallery`
* `Rating`
* `PriceTag`
* `HostInfo`
* `AmenitiesList`
* `BookingCard`
* `BottomNavigation`

Cada componente debe tener una responsabilidad clara y recibir datos por props cuando sea necesario.

## Datos necesarios

Cada alojamiento puede necesitar datos como:

* id
* título
* ubicación
* descripción breve
* descripción completa
* imágenes
* precio por noche
* rating
* cantidad de reseñas
* anfitrión
* servicios
* categoría
* cantidad de huéspedes
* habitaciones
* camas
* baños

Durante esta etapa se pueden usar datos mockeados en archivos locales.

## Navegación

La navegación debe permitir moverse entre:

* `/`
* `/search`
* `/rooms/[id]`

La navegación debe funcionar sin recargar el navegador, usando `Link` de Next.js.

## Criterios técnicos

* Usar Next.js 16 con App Router.
* Usar TypeScript.
* Usar Tailwind CSS.
* Mantener diseño mobile-first.
* Adaptar a escritorio desde 768px.
* Evitar componentes grandes con demasiadas responsabilidades.
* Mantener la UI en español.
* Usar datos locales/mockeados.
* No implementar backend ni autenticación.
* Priorizar estructura clara, legibilidad y reutilización.

## Uso de prompts de visión

Antes de implementar las vistas finales, se usarán capturas de pantalla de la interfaz original de Airbnb como referencia visual. A partir de esas capturas se generará una especificación de componentes con ayuda de IA, y esa especificación servirá como guía para construir la interfaz.

## Resultado esperado

El resultado final será un prototipo navegable de tres vistas inspirado en Airbnb, construido con componentes reutilizables de React y una estructura clara de Next.js. El proyecto debe demostrar comprensión de diseño responsive, composición de componentes y navegación entre páginas.


## Especificaciones generadas desde capturas de Airbnb mobile

### Vista 1: Home `/`

```tsx
/*
Vista: Home mobile

Componentes principales:

1. MobileSearchHeader
Props:
- searchValue: string
- onSearchChange: (value: string) => void

Layout:
- Barra superior centrada.
- Campo de búsqueda tipo píldora con ícono de lupa.
- Debe ocupar casi todo el ancho disponible.
- En mobile se muestra arriba de todo.

2. CategoryTabs
Props:
- categories: Category[]
- activeCategory: string
- onCategoryChange: (category: string) => void

Layout:
- Fila horizontal scrolleable.
- Cada item tiene ícono + etiqueta.
- La categoría activa se resalta visualmente.

3. SectionHeader
Props:
- title: string
- subtitle?: string

Layout:
- Título en negrita.
- Opcionalmente subtítulo descriptivo.
- Botón circular con flecha hacia la derecha.

4. PropertyCard
Props:
- property: Property

Layout:
- Imagen rectangular con bordes redondeados.
- Badge superior “Favorito entre huéspedes”.
- Botón de favorito en la esquina superior derecha.
- Debajo: título, precio y rating.

5. BottomNavigation
Props:
- activeItem: string

Layout:
- Barra fija inferior en mobile.
- Ítems: Explora, Favoritos, Iniciar sesión.
*/
```

### Vista 2: Catálogo `/catalog`

```tsx
/*
Vista: Catálogo mobile

Componentes principales:

1. CatalogHeader
Props:
- title: string
- subtitle: string

Layout:
- Botón volver a la izquierda.
- Campo tipo píldora con destino y detalles de búsqueda.
- Botón de filtros a la derecha.

2. MapPreview
Props:
- properties: Property[]

Layout:
- En mobile aparece arriba o debajo del listado.
- Placeholder de mapa con fondo visual.
- Puede mostrar pins simulados con precios.

3. CatalogResultsHeader
Props:
- totalResults: number
- sortOrder: "asc" | "desc"
- onSortChange: (value: "asc" | "desc") => void

Layout:
- Muestra cantidad de resultados.
- Selector para ordenar por precio ascendente o descendente.

4. FeeNotice
Props:
- text: string

Layout:
- Caja informativa con ícono.
- Texto: “Los precios incluyen todas las tarifas”.

5. PropertyCard
Props:
- property: Property

Layout:
- Se reutiliza la tarjeta de alojamiento.
- Al hacer clic navega hacia /rooms/[id].
*/
```

### Vista 3: Detalle `/rooms/[id]`

```tsx
/*
Vista: Detalle de habitación mobile

Componentes principales:

1. RoomTopBar
Props:
- onBack?: () => void

Layout:
- Botón volver a la izquierda.
- Botones compartir y favorito a la derecha.
- Posicionados sobre la imagen principal.

2. ImageGallery
Props:
- images: string[]
- currentIndex: number
- onPrevious: () => void
- onNext: () => void

Layout:
- Imagen grande superior.
- Indicador tipo “1 / 36”.
- Botones para cambiar imagen.

3. RoomHeader
Props:
- title: string
- type: string
- location: string
- guests: number
- bedrooms: number
- beds: number
- bathrooms: number
- rating: number
- reviews: number

Layout:
- Título grande.
- Subtítulo con tipo de alojamiento y ubicación.
- Línea con huéspedes, habitaciones, camas y baños.
- Rating y reseñas.

4. HostInfo
Props:
- hostName: string
- hostYears: number
- avatarUrl?: string

Layout:
- Avatar circular.
- Nombre del anfitrión.
- Años como anfitrión.

5. AmenitiesGrid
Props:
- amenities: Amenity[]

Layout:
- Grilla de servicios.
- Cada servicio tiene ícono + etiqueta.

6. BookingCard
Props:
- pricePerNight: number
- guests: number
- minGuests: number
- maxGuests: number
- onIncreaseGuests: () => void
- onDecreaseGuests: () => void

Layout:
- Card fija o destacada en la parte inferior.
- Precio por noche.
- Contador de huéspedes.
- Botón principal “Reserva”.
*/
```
