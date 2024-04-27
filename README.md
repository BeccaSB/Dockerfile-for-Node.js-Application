# Dockerfile for Node.js Application

This Dockerfile is designed to package a Node.js application into a Docker container. It utilizes an official Node.js runtime image as the base and sets up the necessary environment to run the application.

## Usage

To use this Dockerfile:

1. Ensure Docker is installed on your local machine.
2. Place the Dockerfile in the root directory of your Node.js application.
3. Run the following command in the terminal to build the Docker image:
   ```
   docker build -t <image-name> .
   ```
   Replace `<image-name>` with your desired image name.
4. After the image is built successfully, you can run a container using the following command:
   ```
   docker run -p 3000:3000 <image-name>
   ```
   This will start the Node.js application in a Docker container, and you can access it at `http://localhost:3000`.

## Dockerfile Explanation

- **FROM node:14**: Sets the official Node.js runtime image as the base.
- **WORKDIR /usr/src/app**: Sets the working directory in the container to `/usr/src/app`.
- **COPY package*.json ./**: Copies `package.json` and `package-lock.json` from the local directory to the container's working directory.
- **RUN npm install**: Installs dependencies defined in `package.json`.
- **COPY . .**: Copies the rest of the project files to the container's working directory.
- **EXPOSE 3000**: Exposes port 3000, which the Node.js application runs on.
- **CMD ["npm", "start"]**: Defines the command to run the application when the container starts.

## License

This Dockerfile is provided under the MIT License. See the [LICENSE](LICENSE) file for details.
