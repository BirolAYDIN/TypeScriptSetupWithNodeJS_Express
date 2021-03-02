### TypeScript Setup With Node & Express Server Example

Let's load TypeScript globally first
```bash
   npm i -g typescript@next   // latest version published daily
```

You can try to make sure typescript is loaded
```bash
  tsc --version
```

Let's create source folder and work file
```bash
  src/app.ts
```

For the TypeScript configuration file
```bash
  tsc --init     // tsconfig.json file
```

TypeScript configuration file can be used briefly as in the repo or according to your request

- You can output javascript to TypeScript file with tsc command.
```bash
   tsc   //  app.ts ---> app.js
```

Let's create the package.json file
```bash
  npm init -y
```

We install npm i express with express
```bash
  npm i express
```

For other addictions

```bash
  npm i -D typescript ts-node nodemon @types/node @types/express
```

Edit package.json file scripts

```json
   "scripts": {
		"start": "node dist/app.js",
		"dev": "nodemon src/app.ts",
		"build": "tsc -p ."
  }
```

The app.ts file is prepared

```javascript
  import express, {Application, Request, Response, NextFunction} from 'express';

const app:Application = express();

app.get('/', (req: Request, res: Response, next: NextFunction) => {
	res.send('Hello world');
});


app.listen(5000, () => console.log('Server running'));
```

Use the command below to test

```bash
   npm run dev 
```

To get build and run

```bash
  npm run build
```