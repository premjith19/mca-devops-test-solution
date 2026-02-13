FROM node:20.18.0 AS build

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm i --force
# Copy application code
COPY . .

# Build the application
RUN npm run build

# Stage 2: Serve the app using Nginx
FROM nginx:alpine

# Copy build output to Nginx's HTML directory
COPY --from=build /app/dist/frontend/browser/ /usr/share/nginx/html

# Copy custom Nginx configuration if needed
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Expose port
EXPOSE 80

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]