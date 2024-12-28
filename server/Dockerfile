# Use official Node.js image
FROM node:18-alpine

# Set working directory inside container
WORKDIR /usr/src/app

# Install pnpm globally
RUN npm install -g pnpm

# Install NestJS CLI globally
RUN npm install -g @nestjs/cli

# Copy the pnpm-lock.yaml and package.json from the server folder
COPY ./pnpm-lock.yaml ./pnpm-lock.yaml
COPY ./package.json ./package.json

# Install dependencies using pnpm
RUN pnpm install --frozen-lockfile --verbose

# Copy the entire server folder into the container
COPY . /usr/src/app

# Expose the port the app will run on
EXPOSE 3000

# Start the app in production mode
CMD ["pnpm", "run", "start:dev"]
