FROM node:14-alpine AS build-base

# set our node environment, either development or production
# defaults to production, compose overrides this to development on build and run
ARG NODE_ENV=production
ENV NODE_ENV $NODE_ENV

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
COPY package.json ./
RUN npm i

# Copy in the source
COPY . .

# T E S T
# =======
#
# Add a test environment to the service above:
#
FROM build-base AS test

# Run the tests
ENTRYPOINT ["npm", "test"]
