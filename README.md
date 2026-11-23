# Prácticas de React y Redux

Aplicación de ejercicios para practicar la construcción de interfaces con React y la gestión de estado global con Redux. El proyecto reúne ejemplos pequeños e independientes —contador, perfil, frutas, tareas y publicaciones— dentro de una misma aplicación.

## Stack y herramientas

- **JavaScript** y **JSX** para la lógica y la interfaz.
- **React 18** para construir la aplicación con componentes funcionales.
- **Redux 5** para mantener el estado global, organizarlo con reducers y actualizarlo mediante acciones.
- **React Redux** para conectar los componentes al store con `Provider` y `connect`.
- **Redux Thunk** para despachar operaciones asíncronas, como un contador con demora y la carga de publicaciones.
- **Redux Logger** y **Redux DevTools Extension** para observar las acciones y el estado durante el desarrollo.
- **Create React App** (`react-scripts`) como entorno de desarrollo y herramienta de build.
- **react-spinners** para mostrar un indicador mientras se cargan publicaciones.
- **JSONPlaceholder** como API pública de prueba para obtener publicaciones.

El proyecto también declara otras dependencias en `package.json`; no todas forman parte de las funcionalidades implementadas actualmente.

## Funcionalidades y conceptos practicados

### Estado global y componentes

`src/redux/store.js` crea el store y aplica middleware. `src/redux/reducers/index.js` combina los reducers de contador, usuario, frutas, tareas y publicaciones. La aplicación entrega el store a sus componentes mediante `Provider`.

Los componentes leen los datos del estado global y despachan acciones usando `connect`, `mapStateToProps` y `mapDispatchToProps`. Los reducers devuelven un estado nuevo al procesar acciones; en los ejemplos se utilizan actualizaciones inmutables con spread, `map` y `filter`.

### Ejercicios de la interfaz

- **Contador:** incrementa y decrementa el valor mediante acciones síncronas; también incluye un incremento asíncrono con una demora configurable.
- **Perfil:** muestra el nombre y el país iniciales, y permite actualizar el nombre desde un campo de texto.
- **Frutas:** permite agregar elementos a una lista almacenada en Redux.
- **Tareas (todos):** permite crear tareas, marcar y desmarcar su estado y eliminarlas. Cada tarea tiene un identificador y una propiedad `checked`.
- **Publicaciones (blog):** solicita publicaciones a JSONPlaceholder, muestra un indicador de carga y presenta los títulos recibidos.

## Estructura del proyecto

```text
src/
├── App.js                    # Composición de la interfaz y Provider de Redux
├── index.js                  # Punto de entrada de React
├── utils.js                  # Utilidad para generar identificadores
├── components/               # Vistas y componentes de cada ejercicio
│   └── Todos/                # Formulario, lista e ítem de tarea
└── redux/
    ├── store.js              # Store y middleware
    ├── actions/              # Creadores de acciones y thunk
    └── reducers/             # Reducers por dominio y reducer raíz
```

## Requisitos

Necesitas tener **Node.js** y **npm** instalados.

## Instalación y ejecución

Desde la raíz del repositorio:

```bash
npm install
npm start
```

El servidor de desarrollo se abre en [http://localhost:3000](http://localhost:3000) y recarga la aplicación al guardar cambios.

## Otros comandos

```bash
npm test       # Ejecuta el entorno de pruebas de Create React App
npm run build  # Genera la versión optimizada en build/
```
