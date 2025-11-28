# Use Node.js official image
FROM node:20-alpine

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install backend dependencies
RUN npm install

# Copy the backend source code
COPY . .

# Expose backend port (as per your app, usually 3000)
EXPOSE 3000

# Start the backend server
CMD ["npm", "start"]
