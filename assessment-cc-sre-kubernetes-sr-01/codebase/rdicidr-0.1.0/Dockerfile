# Etapa de build
FROM node:15 AS builder

# Define o diretório de trabalho
WORKDIR /app

# Copia os arquivos necessários
COPY package.json package-lock.json ./

# Instala dependências
RUN npm install

# Copia o restante dos arquivos da aplicação
COPY . .

# Faz o build da aplicação (se necessário)
RUN npm run build

# Etapa de produção
FROM node:15

# Define o diretório de trabalho
WORKDIR /app

# Copia arquivos do estágio anterior
COPY --from=builder /app /app

# Instala as dependências de produção
RUN npm install --only=production

# Define o comando para iniciar a aplicação
CMD ["npm", "start"]

# Exposição de porta (opcional)
EXPOSE 3000
