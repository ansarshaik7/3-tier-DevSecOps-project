# Stage 1
# Base Image
FROM node:25 AS builder

# Work Directory
WORKDIR /app

# COPY the files
COPY package*.json ./

# clean and install application dependencies
RUN npm install

# Copy all code
COPY . .

# build the app
#RUN npm run build

# Stage 2
# base image
FROM node:alpine

# Cpoy files from builder
COPY --from=builder /app/package*.json ./

# Port expose
EXPOSE 5000

# Start nginx
CMD [ "node", "app.js" ]
