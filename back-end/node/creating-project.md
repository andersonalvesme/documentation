# Creating project

yarn init -y

yarn add express

create file index.js

```javascript
const express = require('express');
const server = express();

// for test you can run 'node index.js' in the root folder.
// console.log(express);

//localhost:3000/curso
server.get('/curso', (req, res) => {
    return res.json({curso: 'Node JS'});
});

server.listen(3000);
```

req: são os dados da requisição.\
res: é o resultado da requisição.

* Query params = parametros no endereço (?tt=tt\&rr=rr)

```javascript
const express = require('express');
const server = express();

server.get('/curso', (req, res) => {
    const nome = req.query.nome;
    
    return res.json({curso: `Curso: ${nome}`});
});

server.listen(3000);
```

* Route params = pararametros na rota (/client/22)

```javascript
const express = require('express');
const server = express();

server.get('/curso/:id', (req, res) => {
    const id = req.params.id;
    
    return res.json({curso: `Id: ${id}`});
});

server.listen(3000);
```

* Request body = no corpo da requisição {nome: "aa", idade: "bb"}

Live reload: nodemon -> yarn add nodemon -D\
\-- For run **nodemon index.js**\
add in package.json:\
...cense": "MIT",\
**"scripts": {**\
&#x20; **"dev": "nodemon index.js"**\
**},**\
"dependencies"...\
\-- For run, **yarn dev**

****

Para mandar json via post é necessário habilitar no express, usando o comando:\
server.use(express.json());



* Middlewares - Intermediario entre front e backend.

```javascript
// Middleware Global
server.use((req, res, next) => {
    // Alguma lógica
    // Pode fazer validação de segurança, por exemplo.
    
    console.log(req.url);
    return next();
}
```

```javascript
function checkField(req, res, next) {
    if (!req.body.name) {
        return res.status(400).json({error: "Field is needed"});
    }
    
    return next();
}

// Pode ser adicionado vários middlewares.
server.post('/route', checkField, (req, res) => {
    const {name} = req.body;
    arrayField.push(name);
    
    return res.json(cursos);
});
```
