# Use NodeJS base image
FROM node:13

# Create app directory in Docker
WORKDIR /usr/src/app

# Install app dependencies by copying
# package.json and package-lock.json
COPY package*.json ./

# Install dependencies in Docker
RUN npm ci

# Copy app from local environment into the Docker image
COPY . .

# TypeScript compile
RUN npm install -g typescript
RUN npm run tsc

# Set the API's port number
EXPOSE 8080

# Define Docker’s behavior when the image is run
# Run without TypeScript compile
CMD ["npm", "run", "prod-no-tsc"]