FROM node:16

# Create a non-root user and switch to it
RUN useradd -m appuser
USER appuser

WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .

# Add HEALTHCHECK instruction
HEALTHCHECK --interval=30s --timeout=30s --start-period=5s --retries=3 \
  CMD curl -f http://localhost:3001/health || exit 1

EXPOSE 3001
# Command to run the application
CMD ["node", "index"]
