# Use an official Node.js image as the base image
FROM node:16-alpine

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy the entire app into the container
COPY . .

# Expose the backend port (e.g., 5000)
EXPOSE 5000

# Start the backend server
CMD ["npm", "start"]
