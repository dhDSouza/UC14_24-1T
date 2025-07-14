# 🧩 Atividade: Publicação de Projeto Fullstack no Vercel com SQLite

## 🎯 Objetivo

Publicar um projeto fullstack (com backend em TypeScript/Node + TypeORM e frontend) no **Vercel**, realizando a **troca do banco de dados MySQL para SQLite** para garantir compatibilidade com ambientes serverless como o Vercel.

---

## 📋 O que fazer?

1. Escolha um projeto **fullstack** já feito anteriormente (com autenticação, CRUD, etc.).
2. **Troque o banco de dados** de MySQL para SQLite usando TypeORM.
3. Faça o deploy no **Vercel**.
4. Envie o link público da aplicação + link do repositório GitHub com as alterações feitas.

---

## 🧰 Tutorial: Como trocar de MySQL para SQLite no TypeORM

O projeto usa `typeorm` com `mysql`, e a alteração para `sqlite` é simples.

### 📦 1. Instale o driver do SQLite

Abra o terminal e rode:

```bash
npm uninstall mysql2
npm install sqlite3
```

---

### ⚙️ 2. Altere o arquivo de configuração do TypeORM (`data-source.ts`)

```ts
import { DataSource } from "typeorm";

export const AppDataSource = new DataSource({
  type: "sqlite", // ✅ troca de "mysql" para "sqlite"
  database: "database.sqlite", // ✅ nome do arquivo SQLite
  synchronize: true,
  logging: false,
  entities: ["src/models/**/*.ts"],
  migrations: ["src/migrations/**/*.ts"],
  subscribers: [],
});
```

> [!TIP]   
> Não esqueça de remover as variáveis relacionadas ao MySQL (`DB_HOST`, `DB_PORT`, etc.) no `.env` e atualizar o código que depende delas.

---

### 📁 3. Garanta que o arquivo `database.sqlite` esteja no `.gitignore`

```bash
# .gitignore
database.sqlite
```

> [!NOTE]
> Mas atenção: **no Vercel**, o banco pode ser regenerado a cada deploy. Portanto, o foco é mais demonstrativo/teste, não produção.

---

### 🚀 4. Deploy no Vercel

1. Crie um repositório no GitHub com o projeto.
2. Vá até [https://vercel.com/import](https://vercel.com/import) e conecte o repositório.
3. Nas configurações de build:

   * **Framework**: Node.js
   * **Build Command**: `npm run build`
   * **Output Directory**: `dist`
4. O Vercel detectará e fará o deploy.
5. Após a publicação, teste sua API no link fornecido.

---

## ✅ Entrega

Envie no formulário:

* 🔗 Link da aplicação no Vercel
* 🧠 Breve resumo das alterações feitas (principalmente a troca para SQLite)
* 📁 Link do repositório GitHub
