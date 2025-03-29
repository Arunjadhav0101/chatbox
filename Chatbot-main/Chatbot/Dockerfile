# Use Node.js as base image
FROM node:18-alpine

# Set the working directory
WORKDIR /app

# Copy only package.json and package-lock.json first (improves caching)
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the project files
COPY . .

# Build the project (if applicable)
RUN npm run build

# Expose the port (adjust if needed)
EXPOSE 5000

# Start the application
CMD ["npm", "run", "preview", "--", "--host", "0.0.0.0", "--port", "5000"]

