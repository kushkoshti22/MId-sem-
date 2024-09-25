# Use the official Node.js image as the base
FROM node:16-alpine AS build

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json to install dependencies
COPY package*.json ./
RUN npm install

# Copy the entire frontend application to the container
COPY . .

# Build the React application
RUN npm run build

# Serve the built app (using a simple server)
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
