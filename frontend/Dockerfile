# Stage 1: Build the React app
FROM node:20 AS build

# Set working directory inside the container
WORKDIR /app

# Set the memory limit to 2GB
ENV NODE_OPTIONS="--max-old-space-size=2048"

# Copy package.json and package-lock.json for dependency installation
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Copy the rest of the app files to the container
COPY . .

# Build the React app for production
RUN npm run build

# Stage 2: Serve the production build using Nginx
FROM nginx:alpine

# Copy the build output from the previous stage to Nginx's HTML directory
COPY --from=build /app/dist /usr/share/nginx/html

# Expose port 80 for the Nginx server
EXPOSE 80

# Start Nginx when the container starts
CMD ["nginx", "-g", "daemon off;"]


# # Stage 1: Build the React app
# FROM node:20 AS build

# # Set working directory inside the container
# WORKDIR /app

# # Copy package.json and package-lock.json for dependency installation
# COPY package.json package-lock.json ./

# # Install dependencies
# RUN npm install

# # Copy the rest of the app files to the container
# COPY . .

# # Build the React app for production
# RUN npm run build

# # Stage 2: Serve the production build using Nginx
# FROM nginx:alpine

# # Copy the build output from the previous stage to Nginx's HTML directory
# COPY --from=build /app/dist /usr/share/nginx/html

# # Expose port 80 for the Nginx server
# EXPOSE 80

# # Start Nginx when the container starts
# CMD ["nginx", "-g", "daemon off;"]



# # Use an official Node.js image as the base image
# FROM node:20

# # Set the working directory inside the container
# WORKDIR /app

# # Copy package.json and package-lock.json to the working directory
# COPY package.json package-lock.json ./

# # Install dependencies
# RUN npm install

# # Copy the rest of the application files to the working directory
# COPY . .

# # Build the application
# RUN npm run build

# # Expose port 5173 (default Vite dev server port)
# EXPOSE 5173

# # Start the application using Vite's preview mode
# CMD ["npm", "run", "preview"]


# FROM node:20

# WORKDIR /app

# COPY package.json . 

# RUN npm install

# COPY . .

# EXPOSE 5173

# CMD [ "npm","start"]


