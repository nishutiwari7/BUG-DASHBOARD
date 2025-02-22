FROM node:18-alpine as build

WORKDIR /bug_dashboard

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy all frontend code
COPY . .

# Build the app
RUN npm run build

# Production stage with Nginx
FROM nginx:alpine
COPY --from=build /bug_dashboard/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
