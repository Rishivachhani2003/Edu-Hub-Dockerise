# Use the official Node.js 20 image as the base image
FROM node:20-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy only package.json and package-lock.json first to leverage Docker cache
COPY package.json package-lock.json ./ 

# Install the dependencies
RUN npm install

# Copy the rest of the application files to the container
COPY . .

# Expose port 5000 to allow external access to the container
EXPOSE 5000

# Define the command to run the application using nodemon for development
CMD ["npm", "run", "dev"]


# FROM node:20

# WORKDIR /app

# COPY package.json . 

# RUN npm install

# COPY . .

# EXPOSE 5000

# CMD [ "npm","run","dev" ]



