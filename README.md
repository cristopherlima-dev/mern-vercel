# mern-vercel

## Baseado no projeto

[https://www.youtube.com/watch?app=desktop&v=GyDAGGUn3Ck](https://www.youtube.com/watch?app=desktop&v=GyDAGGUn3Ck)

## Criação do projeto

```bash
### Clonar o projeto
git clone git@github.com:cristopherlima-dev/mern-vercel.git

### Preparação do diretório api
cd mern-vercel
mkdir api
cd api
npm init -y
npm i express
npm i --save-dev nodemon
npm i cors

### Preparação do diretório client
cd ..
npm create vite@latest
## Project name: client
## Select a framework: React
## Select a variant: JavaScript
cd client
npm i
```

## Criar o arquivo `vercel.json` no diretório root

```json
{
  "buldCommand": "cd client && npm install && npm run build",
  "outputDirectory": "client/dist",
  "framework": "vite",
  "rewrites": [
    {
      "source": "/api/(.*)",
      "destination": "/api/index.js"
    }
  ]
}
```

## Teste - api

```bash
cd api
npm run dev
```

- No browser: http://localhost:8000/api/hello

## Teste - client

```bash
cd client
npm run dev
```

- No browser: http://localhost:3000

## Criação da build

```bash
cd client
npm run build
```

## Deploy na Vercel

- Add New Project
- Selecionar o projeto `mern-vercel`
- Import
- Deploy
