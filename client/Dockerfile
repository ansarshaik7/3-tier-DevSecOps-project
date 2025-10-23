# Stage 1
# Base Image
FROM node:25 AS builder

# Work Directory
WORKDIR /app

# COPY the files
COPY package*.json ./

# clean and install application dependencies
#RUN npm ci
RUN npm install

# Copy all code
COPY . .

# build the app
RUN npm run build

# Stage 2
# nginx base image
FROM nginx:alpine

# Cpoy files from builder
COPY --from=builder /app/build /usr/share/nginx/html

COPY nginx/default.conf /etc/nginx/conf.d/default.conf

# Port expose
EXPOSE 80

# Start nginx
CMD [ "nginx", "-g", "daemon off;" ]
