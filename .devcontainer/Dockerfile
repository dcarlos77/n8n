# Use a imagem base oficial do N8N
FROM n8nio/n8n:latest

# Adiciona pacotes adicionais, se necessário (se não precisar, pode remover)
RUN apk add --no-cache --update openssh sudo shadow bash

# Define variáveis de ambiente padrão (pode ser sobrescrito via Render)
ENV N8N_BASIC_AUTH_ACTIVE=true
ENV N8N_BASIC_AUTH_USER=admin
ENV N8N_BASIC_AUTH_PASSWORD=admin
ENV N8N_PORT=5678
ENV WEBHOOK_URL=https://your-webhook-url/

# Expõe a porta padrão do N8N
EXPOSE 5678

# Comando para iniciar o N8N
CMD ["n8n"]

# Use uma imagem com Node.js na versão correta
FROM node:18

# Instale dependências adicionais e copie arquivos
RUN apt-get update && apt-get install -y \
    openssh-client \
    bash \
    sudo

# Instale n8n globalmente
RUN npm install -g n8n

# Exponha a porta usada pelo N8N
EXPOSE 5678

# Comando para iniciar o N8N
CMD ["n8n"]
