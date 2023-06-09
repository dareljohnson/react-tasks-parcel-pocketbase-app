## Project Title

### React with Parcel and Pocketbase Course

## Project Description

This repository contains the source code to develop and build a fully functional React app, using Parcel as a package management and build system, and pocketbase as a backend system.

## How to Install

Requirements:

- parcel v2.9.2
- node v18.15.0
- npm v9.5.0
- react v18.2.9
- react-dom v18.2.4
- tailwindcss v3.3.2s
- TypeScript v5.1.3

Optional:

pocketbase: 
https://pocketbase.io/

## How to Use the Project

On your Windows file system create a new project folder:

```
mkdir react-tasks-pocketbase-app

cd react-tasks-pocketbase-app
```

Initialze a local git repository:

```
git init
```

Initialze node project:

```
npm init -y
```

Install react and react-dom into your project:

```
npm install react react-dom
```

Add TypeScript support:

```
npm install @types/react @types/react-dom --dev
```

Create a tsconfig.json file:

```
notepad tsconfig.json
```

...and add the following

```
{
  "compilerOptions": {
    "jsx": "react",
    "experimentalDecorators": true,
    "isolatedModules": true
  }
}
```

Add tailwind CSS framework to the project:

```
npm install tailwindcss postcss autoprefixer --dev
```

Add tailwind dependencies for React:

```
npm install @headlessui/react @heroicons/react
```

Create a configuration file called .postcssrc:

```
notepad .postcssrc
```

...and add the following

```
{
  "plugins": {
    "tailwindcss": {}
  }
}
```

Create a configuration file called tailwind.config.js:

```
notepad tailwind.config.js
```

...and add the following:

```
module.exports = {
  content: ["./src/**/*.{js,jsx,ts,tsx}"],
  theme: {
    extend: {},
  },
  variants: {},
  plugins: [],
};
```

Install Parcel (build management) to your project:

```
npm install --save-dev parcel
```

Add external SVG support:

```
npm install @parcel/transformer-svg-react --dev
```

Create a configuration file called .parcelrc:

```
notepad .parcelrc
```

...and add the following

```
{
  "extends": "@parcel/config-default",
  "transformers": {
    "*.svg": ["...", "@parcel/transformer-svg-react"],
    "*.{ts,tsx}": ["@parcel/transformer-typescript-tsc"]
  }
}
```

Create a /src directory:

```
mkdir src
```

Create a HTML file in the /src directory:

```
notepad ./src/index.html
```

...and paste in the following html

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Parcel + React + TS</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.tsx"></script>
  </body>
</html>
```

Add Inter Font family for all tailwind UI examples to index.html:

```
<link rel="stylesheet" href="https://rsms.me/inter/inter.css">
```

Add favicon icon (https://www.favicon.cc/):

Download favicon and copy and paste to /src/assets directory

...paste html tag to index.html

```
<link rel="icon" type="image/x-icon" href="/src/assets/favicon.ico">
```

Create an main.tsx file in /src directory:

```
notepad ./src/main.tsx
```

...and paste the following:

```
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.tsx'
import './index.css'

ReactDOM.createRoot(document.getElementById('root') as HTMLElement).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
)
```


Create an index.css file:

```
notepad ./src/index.css
```

...add the following

```
@tailwind base;
@tailwind components;
@tailwind utilities;

/* Path: src\App.css */
```


Create an App.css file:

```
notepad ./src/App.css
```

...and paste the following

```
#root {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.react:hover {
  filter: drop-shadow(0 0 2em #61dafbaa);
}

@keyframes logo-spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@media (prefers-reduced-motion: no-preference) {
  a:nth-of-type(2) .logo {
    animation: logo-spin infinite 20s linear;
  }
}

.card {
  padding: 2em;
}

.read-the-docs {
  color: #888;
}
```

Create an App.tsx file

```
notepad ./src/App.tsx
```

...and paste in the following:

```
import { useState } from 'react'
import reactLogo from './assets/react.svg'
import './App.css'
import React from 'react'

function App() {
  const [count, setCount] = useState(0)

  return (
    <>
      <div>
        <a href="https://react.dev" target="_blank">
          <img src={reactLogo} className="logo react" alt="React logo" />
        </a>
        <a href="https://parceljs.org/recipes/react/" target="_blank">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1068.58691 218.40186" height="100%" fill="currentColor" aria-hidden="true"><path d="M134.10156,41.99756c25.2002,0,42.6001,17.40039,42.6001,42.60059v54.60059c0,25.2002-17.3999,42.60059-42.6001,42.60059H66.90088v76.20117H23.7002V41.99756Zm24,46.80078c0-18.6001-10.80029-29.40039-29.40039-29.40039H42.30029V240.6001h6V164.39893h80.40088c18.6001,0,29.40039-10.7998,29.40039-29.40039ZM128.70117,65.39795c15.00049,0,23.40039,8.40039,23.40039,23.40039v46.2002c0,15.00049-8.3999,23.40039-23.40039,23.40039H48.30029v-93.001Zm-5.3999,75.60107c6.6001,0,10.2002-3.6001,10.2002-10.2002V92.99854c0-6.6001-3.6001-10.2002-10.2002-10.2002H66.90088V140.999Z" transform="translate(-23.7002 -40.79785)"></path><path d="M223.79834,258.00049H179.09766L248.69873,41.99756h50.40039L368.7002,258.00049h-46.501l-14.09961-48.60156H238.19873ZM343.19922,240.6001l-55.5-181.20215H260.09863L203.69824,240.6001h5.7002l15-48.60059H322.7998L337.499,240.6001ZM263.69873,65.39795,226.19824,185.99951H320.999L284.09912,65.39795Zm9.8999,24.00049,22.80029,79.20068h-46.2002Z" transform="translate(-23.7002 -40.79785)"></path><path d="M509.99512,258.00049l-34.7998-80.10107H440.39453v80.10107h-43.2002V41.99756H507.2959c25.2002,0,42.59961,17.40039,42.59961,42.60059v50.70068c0,20.3999-11.39941,35.7002-29.39941,40.80029l36,81.90137Zm18.90039-17.40039-34.7998-79.80127h7.7998c18.60059,0,29.40039-10.7998,29.40039-29.3999V88.79834c0-18.6001-10.7998-29.40039-29.40039-29.40039H415.79492V240.6001h6V160.79883h66L522.5957,240.6001ZM525.2959,131.39893c0,15-8.40039,23.3999-23.40039,23.3999H421.79492V65.39795h80.10059c15,0,23.40039,8.40039,23.40039,23.40039Zm-28.80078,6.2998c6.60059,0,10.2002-3.6001,10.2002-10.2002v-34.5c0-6.6001-3.59961-10.2002-10.2002-10.2002H440.39453v54.90039Z" transform="translate(-23.7002 -40.79785)"></path><path d="M697.49316,91.79834c0-6.6001-3.59961-10.2002-10.2002-10.2002h-46.7998c-6.60059,0-10.2002,3.6001-10.2002,10.2002V208.19971c0,6.59961,3.59961,10.19922,10.2002,10.19922H687.293c6.60059,0,10.2002-3.59961,10.2002-10.19922V181.79932h43.20117V216.6001c0,25.19922-17.40039,42.59961-42.60059,42.59961H629.69238c-25.2002,0-42.59961-17.40039-42.59961-42.59961V83.39844c0-25.20068,17.39941-42.60059,42.59961-42.60059h68.40137c25.2002,0,42.60059,17.3999,42.60059,42.60059v34.80029H697.49316Zm-4.7998-27.6001c15,0,23.40039,8.3999,23.40039,23.3999v13.80029h6V87.59814c0-18.6001-10.7998-29.40039-29.40039-29.40039H635.09277c-18.59961,0-29.40039,10.80029-29.40039,29.40039V212.39893c0,18.60059,10.80078,29.40039,29.40039,29.40039h57.60059c18.60059,0,29.40039-10.7998,29.40039-29.40039V199.19971h-6v13.19922c0,15.001-8.40039,23.40039-23.40039,23.40039H635.09277c-15,0-23.40039-8.39941-23.40039-23.40039V87.59814c0-15,8.40039-23.3999,23.40039-23.3999Z" transform="translate(-23.7002 -40.79785)"></path><path d="M920.38965,41.99756V82.79834H822.28809v44.40039h79.501V167.999h-79.501v49.20068h98.10156v40.80078H779.08789V41.99756ZM901.78906,240.6001v-6H803.68848v-84.001h79.501v-6.00049h-79.501V65.39795h98.10059v-6H797.68848V240.6001Z" transform="translate(-23.7002 -40.79785)"></path><path d="M1001.68555,41.99756V217.19971h90.60156v40.80078H958.48535V41.99756Zm72.001,198.60254v-6H983.08594V59.39795h-6V240.6001Z" transform="translate(-23.7002 -40.79785)"></path></svg>
        </a>
      </div>
      <h1>Parcel + React</h1>
      <div className="card">
        <button onClick={() => setCount((count) => count + 1)}>
          count is {count}
        </button>
        <p>
          Edit <code>src/App.tsx</code> and save to test HMR
        </p>
      </div>
      <p className="read-the-docs">
        Click on the Parcel and React logos to learn more
      </p>
    </>
  )
}

export default App
```

Update package.json file:

```
{
  "name": "my-project",
  "browserslist": "> 0.5%, last 2 versions, not dead",
  "scripts": {
    "start": "parcel",
    "build": "parcel build --dist-dir public",
    "check": "tsc --noEmit"
  },
  "devDependencies": {
    "parcel": "latest"
  }
}
```

Create an Assets directory:

```
mkdir ./src/assets
```

...and copy the react logo into the assets directory

Create a README.md file 

```
notepad README.md
```

...open README.md in a Markdown editor (ghostwriter in this example).

```
ghostwriter README.md
```

You'll need to add ghostwriter to your system PATH variables in Windows 10 or higher. Locate ghostwriter.exe on your filesystem.

## How to Run the Project

Run the local application server:

```
npm start
```


## How to Build the Project for production

Build and package project for Production:

```
npm run build
```

This will create a new directory called "public" in the root directory.

/public

## Include Credits

Thanks to Monstajoe for his example that was an inspiration for me to build my project. You can find his source code on his guthub repo: https://github.com/monstajoe2002/pocketbase-react-course

## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)

