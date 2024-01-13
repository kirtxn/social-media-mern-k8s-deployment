# Use an official Node.js runtime as a parent image
FROM node:14 as build

# Set the working directory to /app
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install app dependencies
RUN npm install

# Copy the current directory contents to the container at /app
COPY . .

# Build the React app
RUN npm run build

# Use a smaller base image for the production build
FROM nginx:alpine

# Copy the build files to the Nginx web server directory
COPY --from=build /app/build /usr/share/nginx/html

# Expose port 3000 to the outside world
EXPOSE 3000

# Command to run the Nginx server
CMD ["nginx", "-g", "daemon off;"]
