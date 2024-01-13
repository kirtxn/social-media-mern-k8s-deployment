# Use an official Node.js runtime as a parent image
FROM node:14

# Set the working directory to /app
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install app dependencies
RUN npm install

# Copy the current directory contents to the container at /app
COPY . .

# Expose the port that the app runs on
EXPOSE 3001

# Define environment variable for Node.js
ENV NODE_ENV production

# Start the Node.js application
CMD ["npm", "start"]
