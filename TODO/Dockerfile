FROM node:20-alpine

WORKDIR /app

# Copy backend dependencies first
COPY todo_backend/package*.json ./todo_backend/
RUN cd todo_backend && npm install

# Copy frontend dependencies
COPY todo_frontend/package*.json ./todo_frontend/
RUN cd todo_frontend && npm install

# Copy the rest of the project
COPY . .

# Build React frontend
RUN cd todo_frontend && npm run build

# Backend will serve the frontend build
EXPOSE 5000

CMD ["node", "todo_backend/server.js"]
