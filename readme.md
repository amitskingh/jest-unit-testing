# Jest Unit Testing for Node.js + TypeScript

## Project Setup

```bash
npm init -y
npm i typescript ts-node -D
npx tsc --init
npm i express
npm i @types/express @types/node
npm i jest@latest ts-jest@latest @types/jest@latest -D
```

## Configuration

### jest.test.ts

```ts
import type { Config } from "jest";

const config: Config = {
  preset: "ts-jest",
  testEnvironment: "node",
  /* 
  'node' → Best for backend tests (e.g., APIs, databases).
  'jsdom' → Used for frontend tests (browser-like behavior).
*/
  testMatch: ["**/tests/**/*.test.ts"],
  /*
  directory structure for testing files in this case it is /tests and looking within the files of type .test.ts
*/
  clearMocks: true,
};

export default config;
```

### package.json

```json
 "scripts": {
    "build": "rimraf dist && tsc",
    "start": "node dist/app.js",
    "dev": "nodemon dist/app.js",
    "test": "jest",
    "test:watch": "jest --watch"
  },
```

## Testing

```bash
npm test
```
