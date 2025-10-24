Claro! Aqui está o conteúdo formatado de forma clara, organizada e com estilo Markdown profissional:

---

# 🐳 O que é Docker?

Docker é um software que ajuda os desenvolvedores a resolver um dos maiores problemas dos projetos: **diferenças de ambiente**.  
Sabe aquela famosa frase “na minha máquina funciona”? Pois é — o Docker veio pra acabar com isso.

---

## 📦 Conceitos básicos

### 🔹 Imagem
Uma imagem é como um pacote com tudo que o projeto precisa: código, dependências, configurações, etc.  
É a base para criar os contêineres.

### 🔹 Contêiner
É a imagem em execução. Um contêiner roda isolado, como se fosse uma mini máquina virtual — mas muito mais leve e rápida.

### 🔹 Dockerfile
É um arquivo que descreve como montar uma imagem. Nele você define o que instalar, copiar e executar.

#### 🧱 Exemplo de Dockerfile

```Dockerfile
# Imagem base com Node.js
FROM node:18

# Diretório de trabalho dentro do contêiner
WORKDIR /app

# Copia os arquivos de dependência
COPY package*.json ./

# Instala as dependências
RUN npm install

# Copia o restante do código
COPY . .

# Compila o TypeScript
RUN npm run build

# Expõe a porta da API
EXPOSE 3000

# Comando para iniciar a API
CMD ["node", "build/index.js"]
```

---

## 🍳 Analogia Culinária

| Elemento           | Equivalente Docker   | Descrição                                                                 |
|--------------------|----------------------|---------------------------------------------------------------------------|
| Receita            | `Dockerfile`         | Instruções passo a passo para preparar o ambiente da aplicação.          |
| Livro de receitas  | Imagem Docker        | Resultado do build do Dockerfile. Contém tudo que foi definido na receita. |
| Prato pronto       | Contêiner Docker     | Execução da imagem. É onde sua aplicação realmente roda.                 |

---

## 🧭 Passo a passo

### 1. Abrir o projeto no VS Code

![VSCode](/imgs/image1.png)




### 2. Criar a imagem Dockerfile

```bash
docker build -t api_nutriacess .
```

![alt text](/imgs/image2.png)
![alt text](/imgs/image-1.png)



### 3. Verificar se a imagem foi criada

```bash
docker images
```
![alt text](/imgs/image4.png)

### 4. Executar a imagem (criar um contêiner para o backend)

```bash
docker run -p 3003:3003 api_nutriacess
```

![alt text](/imgs/image3.png)

![alt text](/imgs/image5.png)