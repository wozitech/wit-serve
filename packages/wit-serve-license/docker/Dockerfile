FROM node:12-buster

# # Create app directory
WORKDIR /usr/src/app

RUN git clone https://github.com/wozitech/wit-serve.git /usr/src/app

WORKDIR /usr/src/app/packages/wit-serve-license/

# # Install the application dependencies
RUN npm install
# # If you are building your code for production
# # RUN npm ci --only=production

# build the typescript app
RUN npm run build

# backend API starts up on port 8080
EXPOSE 8080

# environment variables
ENV NODE_ENV production
ENV PORT 8080

# now start SFC backend app
WORKDIR /usr/src/app/packages/wit-serve-license/dist
CMD ["node", "index.js"]
