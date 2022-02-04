# p5js-template

Template for [p5.js](https://p5js.org/) sketches using VS Code.

## About

Template project for creating p5.js sketches using the following tools:

- Code editor: [Visual Studio Code](https://code.visualstudio.com/)
- Code formatter: [Prettier](https://prettier.io/)
- Linter: [ESLint](https://eslint.org/)
- Sketch scaffolding: [Hygen](https://www.hygen.io/)

## Preparation

Install the following tools.

- [Visual Studio Code](https://code.visualstudio.com/)
- [Node.js](https://nodejs.org/)

Next, install the following VS Code extensions. These extensions will be automatically recommended when you open your project in VS Code.

- [Live Preview](https://marketplace.visualstudio.com/items?itemName=ms-vscode.live-server)
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

Finally, install the dependent packages. In the root directory of your project, run the following command.

```sh
npm install
```

Now every time you save a file, the code formatting and linting will run automatically.

## Usage

### Create a new sketch

To create a new sketch, first generate the necessary files from the template. In the root directory of your project, run the following command.

```sh
npm run new <sketch name>
```

When you run it, it will create a `src/<sketch name>` directory containing HTML and JavaScript files.

Let's take a look at the contents of the directory.  
`index.html` contains the code to load [sanitize.css](https://csstools.github.io/sanitize.css/), p5.js, and `sketch.js` in the same directory. Basically, you won't touch this file, but you can add scripts such as [p5.js libraries](https://p5js.org/libraries/) if you want.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>my-awesome-sketch</title>
    <link rel="stylesheet" href="https://unpkg.com/sanitize.css" />
    <script src="https://cdn.jsdelivr.net/npm/p5@latest/lib/p5.js"></script>
  </head>
  <body>
    <script src="./sketch.js"></script>
  </body>
</html>
```

`sketch.js` contains the sketch template code. Here you can mouse over p5.js methods and variables to see their descriptions. Code autocompletion is also enabled.

```js
/// <reference path="../../node_modules/@types/p5/global.d.ts" />

function setup() {
  createCanvas(800, 800);
  background(30);
}

function draw() {
  ellipse(mouseX, mouseY, 80, 80);
}

function keyReleased() {
  if (key === "s") {
    save("sketch");
  }
}
```

### Live preview

You can easily preview your sketch with the [Live Preview](https://marketplace.visualstudio.com/items?itemName=ms-vscode.live-server) extension.

## Sketch template (Optional)

`_templates` directory contains the sketch templates. You can edit it or add new templates.  
See the [Hygen](https://www.hygen.io/) documentation for details.

## Scripts (Optional)

You can already run automatic code formatting and linting every time you save a file. You can also run them manually with the following commands.

### Code formatting

```sh
npm run format
```

### Linting

```sh
npm run lint

# with autofix
npm run lint:fix
```
