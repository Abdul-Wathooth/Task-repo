# Stage 1: Build Angular app
FROM node:20-alpine as build
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy all source code
COPY . .

# Build Angular app for production
RUN npm run build --prod

# Stage 2: Serve with Nginx
FROM nginx:alpine
# Copy built files from Stage 1
COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
