# Personal Finance — Deploy 🚀

Este repositório contém o **deploy via Docker Compose** do projeto **Personal Finance**, subindo:

- ✅ **Frontend** (Angular + Nginx)
- ✅ **Backend** (ASP.NET Web API)
- ✅ **SQLite persistente** via volume Docker

---

## ✅ Requisitos

Antes de começar, você precisa ter instalado:

- **Docker**
- **Docker Compose**

Verifique se está tudo ok com:

```bash
docker --version
docker compose version
```

🚀 Subir o sistema

Na pasta onde está o arquivo docker-compose.yml, execute:

```bash
docker compose up -d
```

Após subir, acesse:

🌐 Frontend: http://localhost:4200

🧩 Backend (Swagger): http://localhost:8080/swagger

🔄 Atualizar para a versão mais recente

Se as imagens foram atualizadas no GHCR e você quer baixar a versão mais nova:

```bash
docker compose pull
docker compose up -d
```

🛑 Parar o sistema

```bash
docker compose down
```

📦 Ver containers rodando

```bash
docker ps
```

📄 Ver logs

- Backend (API)

```bash
docker logs -f pf-api
```

Frontend (Web)

```bash
docker logs -f pf-web
```

🧹 Resetar o banco de dados (SQLite)

⚠️ Atenção: isso remove os dados persistidos no volume.

```bash
docker compose down -v
docker compose up -d
```

🔐 (Opcional) Login no GHCR
Se as imagens estiverem privadas no GHCR, será necessário autenticar antes de rodar:

```bash
docker login ghcr.io -u SEU_USUARIO
```

📌 Quando pedir a senha, use um GitHub Personal Access Token (PAT) com permissão para ler packages.

🧩 Estrutura do deploy

Este deploy cria:

- pf-web → Frontend Angular rodando em Nginx (porta 4200)

- pf-api → API ASP.NET (porta 8080)

- pf_data → volume persistente com o banco SQLite

✅ Comandos úteis

- Recriar tudo do zero:

```bash
docker compose down
docker compose up -d
```

- Reiniciar apenas os containers:

```bash
docker compose restart
```



