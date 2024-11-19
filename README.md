

---

### **1. Criando o ambiente de trabalho**
1. Crie uma pasta no seu computador para o projeto (ex.: `docker-apache-html`).
2. Dentro dessa pasta, crie uma subpasta chamada `html` para armazenar os arquivos da sua aplicação.

---

### **2. Criando os arquivos necessários**

#### **Arquivo HTML**
1. Dentro da pasta `html`, crie um arquivo chamado `index.html` com o seguinte conteúdo básico:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Docker Apache App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 20%;
            background-color: #f4f4f9;
        }
        h1 {
            color: #4CAF50;
        }
    </style>
</head>
<body>
    <h1>Hello, World! 🚀</h1>
    <p>This is a simple web page served with Docker and Apache.</p>
</body>
</html>
```

---

#### **Arquivo `docker-compose.yml`**
Na pasta principal do projeto, crie o arquivo `docker-compose.yml` com o seguinte conteúdo:
```yaml
version: '3.8'

services:
  apache:
    image: httpd:latest
    container_name: apache_server
    ports:
      - "8080:80"
    volumes:
      - ./html:/usr/local/apache2/htdocs/
```

---

### **3. Executando o projeto**

1. Abra um terminal na pasta principal do projeto.
2. Execute o seguinte comando para iniciar o contêiner:
   ```bash
   docker-compose up -d
   ```
3. Após executar o comando, abra um navegador e acesse: [http://localhost:8080](http://localhost:8080).
   - Você verá sua página HTML renderizada!

---

