FROM mcr.microsoft.com/playwright:v1.56.1-jammy

# Cambiar a usuario root
USER root

# Set working directory
WORKDIR /app

# Dar permisos
RUN chown -R pwuser:pwuser /app

# Volver a usuario seguro
USER pwuser

# Copy package files
COPY --chown=pwuser:pwuser package*.json ./

# Install dependencies
RUN npm install --production

# Copy application files
COPY --chown=pwuser:pwuser . .

# Expose port
EXPOSE 3000

# Start the application
CMD ["node", "server.js"]