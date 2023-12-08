FROM node:14
WORKDIR /app

# Copy package.json and package-lock.json (if available)
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application's source code
COPY src/ ./src/

# Expose port 8080
EXPOSE 8080

# Command to run the app
CMD ["node", "src/app.js"]
