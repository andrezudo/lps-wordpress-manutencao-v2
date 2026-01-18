# Servidor de Desenvolvimento

Com hot-reload - salva o HTML e atualiza sozinho no navegador.

## Rodar

```bash
docker compose up -d --build
```

## Parar

```bash
docker compose down
```

## Acessar as páginas

Abra no navegador:

- http://localhost:8000/curso-agente-fifa/
- http://localhost:8000/curso-gestao-no-futebol/
- http://localhost:8000/especializacao-gestao-no-futebol/
- http://localhost:8000/dev/ (lista todas as páginas)

Só trocar o nome da pasta na URL.

Alterou o HTML? Salva e já atualiza no navegador.

---

## Ngrok (compartilhar link externo)

Pra mostrar pra alguém de fora da sua rede.

### Instalar

```bash
# Linux
curl -sSL https://ngrok-agent.s3.amazonaws.com/ngrok.asc \
  | sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null \
  && echo "deb https://ngrok-agent.s3.amazonaws.com buster main" \
  | sudo tee /etc/apt/sources.list.d/ngrok.list \
  && sudo apt update \
  && sudo apt install ngrok
```

Ou baixa direto: https://ngrok.com/download

### Configurar token (só 1 vez)

1. Cria conta em https://ngrok.com
2. Pega o token em https://dashboard.ngrok.com/get-started/your-authtoken
3. Roda:

```bash
ngrok config add-authtoken SEU_TOKEN_AQUI
```

### Usar

Com o servidor rodando (`docker compose up -d`):

```bash
ngrok http 8000
```

Vai aparecer um link tipo `https://abc123.ngrok-free.app` - manda esse link pra quem quiser ver.
