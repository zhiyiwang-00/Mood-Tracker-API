
# Assignment API

The Assignment API will be used to complete each of the assignments using JavaScript Frameworks.

## Prerequisites
In order to use the API, you will require the following:
1. Install [Git](https://git-scm.com/) 
2. Install [NodeJS LTS](https://nodejs.org/en/) with npm **(It must be the LTS version.)**
3. Create an account on [Glitch](https://glitch.com/) (free)

## Instructions
Follow the instructions below to get your API set up and ready for use.

1. Fork this repository to your GitHub account and clone the forked repository to your computer.
2. Run `npm install` in the root of the cloned repository.

### Deploying to Glitch

1. Go to [Glitch.com](https://glitch.com/) and sign in.
2. In the upper-right corner, select **New Project** > **Import from GitHub**.
3. In the import field, enter the URL of your forked repository (e.g., `https://github.com/your-username/assignment-api`) and click **OK**.
4. Glitch will import the repository and automatically set up the project.
5. Once the project has finished loading, click on **Tools** at the bottom of the screen, then **Terminal**.

### Configuring Environment Variables

1. In the terminal, create an `.env` file to store your API key and environment variables:
   ```bash
   echo "NODE_ENV=production" >> .env
   echo "API_KEY=your-64-character-random-key" >> .env
   ```
2. You can generate a random 64-character API key (e.g., using [passwordsgenerator.net](https://passwordsgenerator.net/)).

3. Close the terminal, and your Glitch project will automatically use the `.env` file with the values set above.

### Starting the API

1. In Glitch, open the `package.json` file and check that the `"start"` script is configured as follows:
   ```json
   "scripts": {
     "start": "json-server --watch db.json --port 3000"
   }
   ```
2. Click the **Show** button in the top-left corner to open your API in a new tab. Your API's URL will be in the format:
   ```
   https://your-glitch-project-name.glitch.me
   ```

## API Key and Authorization Header

To access protected endpoints (such as `POST`, `PUT`, `PATCH`, and `DELETE`), include the `X-API-KEY` header in your requests. The API key should match the one you set in your `.env` file.

### Example Request with `X-API-KEY` Header

Here’s how to include the API key in a request:
```bash
curl -X POST https://your-glitch-project-name.glitch.me/resource -H "X-API-KEY: your-64-character-random-key"
```

## Accessing Endpoints

- **Open Endpoints**: All `GET` endpoints are open to access without the `X-API-KEY` header.
- **Protected Endpoints**: All other methods (`POST`, `PUT`, `PATCH`, and `DELETE`) require the `X-API-KEY` header with the correct API key.

---

# Special thanks to Typicode for json-server

[Github: json-server](https://github.com/typicode/json-server)

---
