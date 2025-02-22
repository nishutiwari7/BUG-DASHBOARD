FROM node:18-alpine

WORKDIR /server

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy backend code
COPY . .

# Create uploads directory
RUN mkdir -p uploads

EXPOSE 3000
CMD ["npm", "run", "start"]
