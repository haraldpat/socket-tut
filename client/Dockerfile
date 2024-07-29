FROM node:16

# Create a non-root user and switch to it
RUN useradd -m appuser

WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .

# Change ownership of the application files to the non-root user
RUN chown -R appuser:appuser /usr/src/app

# Switch to the non-root user
USER appuser

# Add HEALTHCHECK instruction
HEALTHCHECK --interval=30s --timeout=30s --start-period=5s --retries=3 \
  CMD curl -f http://localhost:3000/health || exit 1

EXPOSE 3000
CMD ["npm", "start"]
