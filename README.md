# Tauros
/seguranca-dados
  /public
    index.html
    style.css
  /server
    server.js
  package.json
  <!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Segurança de Dados</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h1>Segurança de Dados</h1>
    <nav>
      <a href="/">Home</a>
      <a href="/servicos">Serviços</a>
      <a href="/blog">Blog</a>
      <a href="/contato">Contato</a>
    </nav>
  </header>

  <main>
    <section>
      <h2>Proteja suas informações</h2>
      <p>Consultoria e soluções em segurança digital para empresas e profissionais.</p>
    </section>
  </main>

  <footer>
    <p>&copy; 2026 Segurança de Dados</p>
  </footer>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  background: #f4f4f4;
  color: #333;
}

header {
  background: #0a3d62;
  color: #fff;
  padding: 15px;
  text-align: center;
}

nav a {
  color: #fff;
  margin: 0 10px;
  text-decoration: none;
}

nav a:hover {
  text-decoration: underline;
}

main {
  padding: 20px;
}

footer {
  background: #222;
  color: #fff;
  text-align: center;
  padding: 10px;
}
const express = require('express');
const path = require('path');
const helmet = require('helmet'); // segurança extra

const app = express();
const PORT = 3000;

// Middleware de segurança
app.use(helmet());

// Servir arquivos estáticos
app.use(express.static(path.join(__dirname, '../public')));

// Rotas simples
app.get('/servicos', (req, res) => {
  res.send('<h1>Serviços</h1><p>Consultoria, auditoria e treinamentos em segurança digital.</p>');
});

app.get('/blog', (req, res) => {
  res.send('<h1>Blog</h1><p>Artigos e dicas sobre proteção de dados.</p>');
});

app.get('/contato', (req, res) => {
  res.send('<h1>Contato</h1><form><input type="text" placeholder="Seu nome"><br><input type="email" placeholder="Seu email"><br><button>Enviar</button></form>');
});

// Inicializar servidor
app.listen(PORT, () => {
  console.log(`Servidor rodando em http://localhost:${PORT}`);
});
{
  "name": "seguranca-dados",
  "version": "1.0.0",
  "main": "server/server.js",
  "scripts": {
    "start": "node server/server.js"
  },
  "dependencies": {
    "express": "^4.18.2",
    "helmet": "^7.0.0"
  }
}
