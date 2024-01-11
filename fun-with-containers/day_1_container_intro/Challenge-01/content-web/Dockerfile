# Start from the node:8 image
FROM node:8

# Set the working directory in the container to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in package.json
RUN npm install

# Make port 3002 available to the world outside this container
EXPOSE 3002

# Run the app when the container launches
CMD ["node", "server.js"]