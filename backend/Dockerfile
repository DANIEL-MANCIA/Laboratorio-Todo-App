# Imagen base optimizada
FROM node:18-alpine

# Establecer directorio de trabajo
WORKDIR /app

# Copiar archivos de dependencias
COPY package*.json ./

# Instalar dependencias
RUN npm install --only=production

# Copiar código fuente (incluyendo la nueva estructura de carpetas)
COPY src/ ./src/

# Exponer puerto
EXPOSE 3000

# Variable de entorno para modo producción
ENV NODE_ENV=production

# Comando de inicio
CMD ["node", "src/index.js"]
