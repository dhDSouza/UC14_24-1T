# 🧠 Aula: Introdução ao Deploy — Colocando Aplicações no Ar

## 🎯 Objetivo da Aula

Ao final da aula serão capazes de:

* Compreender o que é **deploy**.
* Explicar a importância do deploy para aplicações web.
* Diferenciar **deploys estáticos** e **dinâmicos**.
* Entender o **fluxo de um deploy**.
* Realizar o deploy de um site estático com GitHub Pages.
* Conhecer opções de deploy dinâmico (com back-end e banco de dados).

---

## 1️⃣ O que é Deploy?

> **Deploy** é o processo de **colocar uma aplicação em produção**, ou seja, **disponível para o público**, na internet.

* **“Publicar um livro”**: você terminou de escrever (programar), mas ninguém lê se não estiver na livraria (deploy).
* **“Fazer uma comida e não servir”**: você fez o prato (aplicação), mas ele precisa ir à mesa (deploy).

---

## 2️⃣ Por que o Deploy é Importante?

* ✅ Torna o sistema acessível para usuários/clientes.
* ✅ Permite validação real do software.
* ✅ É parte essencial de projetos reais.
* ✅ É onde você testa performance, escalabilidade e segurança de verdade.

---

## 3️⃣ Como Funciona o Processo de Deploy?

### 🔄 Fluxo Simplificado:

1. **Desenvolvimento** → Criação do app localmente.
2. **Build/Empacotamento** → Empacotamento dos arquivos (HTML, CSS, JS, etc.).
3. **Envio ao Servidor** → Upload para uma plataforma de hospedagem (GitHub Pages, Vercel, AWS, etc.).
4. **Configuração** → Domínio, variáveis de ambiente, banco, etc.
5. **Publicação** → Site disponível no ar.

---

## 4️⃣ Tipos de Deploy

### 🧁 A. **Deploy Estático**

* **Sem back-end** (só HTML, CSS, JS).
* Sem necessidade de servidor que processe requisições.
* Ideal para **portfólios, landings pages**, sites informativos.

#### 🧩 Exemplos de plataformas:

* **GitHub Pages** (grátis, simples)
* Vercel (também serve, mas costuma ser para projetos com build)
* Netlify

#### ✅ Vantagens:

* Fácil, rápido, gratuito.
* Menor chance de erro.

---

### 🧨 B. **Deploy Dinâmico**

* Inclui back-end (Node.js, PHP, Python...) e, às vezes, banco de dados.
* O servidor executa código a cada requisição (ex: login, consulta a banco, API).
* Ideal para **sistemas, e-commerces, blogs com painel admin, etc.**

#### ⚙️ Exemplos de serviços:

* **Render**
* **Railway**
* **Vercel** (com back-end via Serverless Functions)
* **Heroku** (limitado atualmente, mas ainda usado)
* **AWS, Azure, GCP** (mais complexos, profissionais)

#### ⚖️ Vantagens x Desvantagens:

| Vantagens               | Desvantagens                     |
| ----------------------- | -------------------------------- |
| Muito mais completo     | Requer mais configurações        |
| Pode ter banco de dados | Pode ter custos                  |
| Suporta APIs            | Mais chance de erros em produção |

---

## 5️⃣ Exemplo Prático: Deploy Estático com GitHub Pages

### 🧪 Exemplo: Portfólio HTML/CSS

#### 📦 Etapas:

1. Crie um repositório no GitHub: `portfolio`
2. Adicione seu código HTML/CSS.
3. Vá em:

   * Settings → Pages → Source: selecione `main` e pasta `/root` ou `/docs`
   * GitHub cria o link: `https://teuusuario.github.io/portfolio/`
4. **Deploy feito!**

### 🔧 Dicas:

* O arquivo principal deve se chamar `index.html`.
* Evite caminhos relativos quebrados.

---

## 6️⃣ Exemplo: Deploy Dinâmico com Render

### 📦 Exemplo: API com Express + Banco de Dados

#### Etapas:

1. Crie conta no [Render](https://render.com)
2. Suba o código em um repositório no GitHub.
3. No Render:

   * Novo Web Service
   * Escolha o repositório
   * Dê build command: `npm install`
   * Start command: `npm start` ou `node index.js`
4. Configure variáveis de ambiente (como `.env`)
5. Configure banco de dados (PostgreSQL integrado, se quiser)

---

## 🚨 Desafios e Cuidados

| Problema              | Solução                                  |
| --------------------- | ---------------------------------------- |
| Variáveis de ambiente | Nunca subir no GitHub, usar `.env`       |
| CORS                  | Configurar backend para aceitar domínios |
| Erros de build        | Conferir dependências e scripts          |
| Banco local quebrando | Usar banco na nuvem ou SQLite            |

---

## 🔁 Bônus: CI/CD (Entrega Contínua)

* Sistemas como **Vercel** ou **Netlify** fazem **deploy automático a cada push no GitHub**.
* Isso facilita testes, correções e atualizações rápidas.

---

## 📚 Conclusão

* Deploy não é só a “cereja do bolo”, é **parte essencial do processo**.
* Todo projeto real vai pra produção.
* Saber fazer deploy te coloca **na frente do mercado**.

---

## 📝 Atividade Sugerida

> **Crie um portfólio simples** (HTML + CSS) e publique com GitHub Pages. Poste o link e compartilhe suas dificuldades.
