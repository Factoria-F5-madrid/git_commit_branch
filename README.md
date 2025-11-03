# Página Web de Ejemplo

Este proyecto es una guía práctica para aprender a usar Git y GitHub con ramas, commits convencionales y resolución de conflictos. A lo largo de esta actividad, crearás una página web simple, trabajarás en múltiples ramas y resolverás conflictos de fusión.

## Objetivos

- Aprender a crear y manejar ramas en Git.
- Usar commits convencionales para mantener un historial de cambios claro.
- Resolver conflictos de fusión en archivos HTML y CSS.

## Prerrequisitos

- Tener Git instalado en tu máquina.
- Tener una cuenta en GitHub.
- Un editor de texto (por ejemplo, VS Code, Atom, Sublime Text).

## Pasos de la Actividad

### 1. Crear un repositorio en github y conectarlo a tu local

Crea una carpeta en tu ordenador:

```sh
mkdir practica-git
```

navegar a ella:

```sh
cd practica-git
```

Y luego de haber creado también un repositorio en github usar los siguientes comandos para conectarlo a tu local:

Inicializa git dentro de tu carpeta>

```sh
git init
```
Crea un archivo de ejemplo (como un README) para tener algo que subir
```sh
echo "# Práctica Git" >> README.md
```
Conecta tu repositorio local con el nuevo repositorio remoto en GitHub (Reemplaza [URL_DEL_REPOSITORIO] con la URL real de tu repo de GitHub)
```sh
git remote add origin [URL_DEL_REPOSITORIO]
```
Renombra la rama local a 'main' si tienes un rama llamad 'Master' en lugar de 'main'
```sh
git branch -M main
```
Añade los archivos al "staging area" de Git
```sh
git add .
```
Confirma (commit) los archivos por primera vez
```sh
git commit -m "first commit"
```
Sube tu código local a GitHub
```sh
git push -u origin main
```

### 2. Crear una rama para la funcionalidad principal

Clona el repositorio en tu máquina local:

```sh
git checkout -b feature/pagina-principal
```

### 3. Crear un archivo HTML y CSS

## Archivos requeridos:

### index.html
```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Página Principal</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Bienvenido a mi página web</h1>
    <p>Esta es una página de ejemplo.</p>
</body>
</html>
```
### style.css

```css
body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    color: #333;
}

h1 {
    color: #007acc;
}
```

### Pasos para Crear y Modificar la Página Web

### 4. Hacer un Commit Convencional
Realiza un commit usando el formato de Conventional Commits:

```sh
git add index.html style.css
git commit -m "feat: crear la estructura inicial de la página principal"
```

### 5. Empujar la Rama al Repositorio Remoto
Empuja la rama al repositorio remoto:

```sh
git push -u origin feature/pagina-principal
```

### 6. Crear una Rama para una Nueva Funcionalidad
Crea una nueva rama para una nueva funcionalidad:

```sh
git checkout -b feature/nueva-seccion
```

### 7. Modificar el HTML para Añadir una Nueva Sección
Añade una nueva sección al `index.html`:

```html
<div>
    <h2>Nueva Sección</h2>
    <p>Contenido de la nueva sección.</p>
</div>
```

### 8. Hacer un Commit Convencional
Realiza un commit usando el formato de Conventional Commits:

```sh
git add index.html
git commit -m "feat: añadir una nueva sección a la página principal"
```

### 9. Crear un Conflicto
Vamos a crear un conflicto editando el mismo párrafo en ambas ramas. Vuelve a la rama `feature/pagina-principal` y edita el `index.html`:

```sh
git checkout feature/pagina-principal
```

Modifica el párrafo:

```html
<p>Esta es una página de ejemplo con información adicional.</p>
```
Haz un commit:

```sh
Copy code
git add index.html
git commit -m "fix: actualizar el contenido del párrafo en la página principal"
```

Haz push a los cambios:

```sh
Copy code
git push origin feature/pagina-principal
```

### 10. Intentar Fusionar y Resolver el Conflicto
Intenta fusionar la rama `feature/nueva-seccion` en `feature/pagina-principal`:

```sh
git checkout feature/pagina-principal
git merge feature/nueva-seccion
```

Git mostrará un conflicto. Abre el `index.html` y resuelve el conflicto editando el archivo para que luzca así, es decir haciendo click en "accept incoming change":

<img width="717" height="350" alt="image" src="https://github.com/user-attachments/assets/33c6aa74-a085-467d-99d8-e331b026e5d9" />

```html
<p>Esta es una página de ejemplo con información adicional y una nueva sección.</p>
<div>
    <h2>Nueva Sección</h2>
    <p>Contenido de la nueva sección.</p>
</div>
```

### 11. Finalizar el Merge
Añade y commitea los cambios resueltos:

- Es normal que en el archivo index aparezca un signo "!" y el nombre en rojo aunque se haya resuelto el conflicto, esto no cambiará hasta que hagas commit.

```sh
git add index.html
git commit -m "merge: resolver el conflicto entre las ramas feature/pagina-principal y feature/nueva-seccion"
```

### 12. Enviar los Cambios al Repositorio Remoto
Envía los cambios al repositorio remoto:

```sh
git push origin feature/pagina-principal
```

### 13. Crear un Pull Request en GitHub (**OPCIONAL**)

1. Ve a GitHub y abre tu repositorio.
2. Verás una opción para crear un Pull Request para la rama `feature/pagina-principal`.
3. Crea el Pull Request siguiendo los pasos que te indique GitHub.
4. Una vez revisado y listo para ser fusionado, haz el merge de la rama `feature/pagina-principal` en `main`.

