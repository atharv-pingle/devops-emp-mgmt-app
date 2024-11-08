# Use the official node image as the base image
FROM node:12.2.0-alpine

# Set the working directory in the container
WORKDIR /app

# Copy the package.json and package-lock.json files to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the remaining source code to the working directory
COPY . .

# Expose port 8000 to the outside world
EXPOSE 3000

# Command to run the application
CMD ["npm", "start"]
