#import the package or software you want for your environment
FROM node:22-alpine 

# Name of the working directory in the container
WORKDIR /app

# Copy the package.json or package-lock.json
COPY package*.json ./

# Run the npm install command
RUN npm install

# Copy rest of my code
# Two dots are important. The first dot represents the current directory (my app directory). The second dot represents my working directory in the container (/app)
COPY . .

# Expose the port on which you want to interact with nginx
EXPOSE 5173

# This is container level, not on build-time. So, not RUN, but CMD
CMD [ "npm", "run", "dev" ]