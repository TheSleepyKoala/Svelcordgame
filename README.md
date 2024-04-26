# Svelcordgame

Svelcordgame is a template repository that seamlessly integrates your Discord Activity with SvelteKit, using a GameMaker HTML5 build to display your Discord activity. This template includes a brick breaker game created with GameMaker to demonstrate the integration.

## Features

-   Easy integration of Discord Activity with SvelteKit
-   GameMaker HTML5 build for interactive content
-   Minimal setup and configuration required
-   Includes a [sample brick breaker game built with GameMaker](https://gamemaker.io/en/blog/remade-brick-breaker-template)

## Prerequisites

-   GameMaker Studio
-   Node.js
-   npm (Node Package Manager)
-   GitHub Desktop (optional, but recommended for easier repository management)

## Getting Started

To get started with Svelcordgame, follow these steps:

1. Click the "Use this template" button on the GitHub repository page to create a new repository based on this template.

2. Clone your newly created repository using GitHub Desktop or the command line:

    ```
    git clone https://github.com/yourusername/your-repo-name.git
    ```

3. Navigate to the project directory:

    ```
    cd your-repo-name
    ```

4. Install the dependencies:

    ```
    npm install
    ```

5. Create a `.env` file in the root directory of the project and add your Discord application's `CLIENT_ID` and `CLIENT_SECRET` for server-side authentication:
    ```
    CLIENT_ID=your_client_id
    CLIENT_SECRET=your_client_secret
    ```

## Setting Up GameMaker WebGL

1. Open your GameMaker project and select the `HTML5` platform.

2. Configure your GameMaker project settings as needed for HTML5 export.

3. Export your GameMaker project as an HTML5 build and locate the generated files.

## Configuration

1. Open your project's `lib` folder and set up your configuration file (`config.ts`) with the necessary details.

2. Copy the GameMaker `html5game` folder you generated earlier and paste it into this project's `static` folder.

## Usage

1. Run the development server to test the project:

    ```
    npm run dev
    ```

2. Open your browser and visit `https://localhost:5173` to see your Discord Activity in action.

3. When you're ready to deploy, build the project:

    ```
    npm run build
    ```

    Note: In the `svelte.config.js` file, make sure to replace `adapter: adapter()` with an adapter of your choice, depending on your deployment platform. SvelteKit offers various official and community adapters for different platforms.

    For example, if you want to use the `@sveltejs/adapter-node` adapter for deploying to platforms that support Node.js (e.g., AWS, Azure, Heroku), you would modify your `svelte.config.js` file like this:

    ```js
    // svelte.config.js
    import { vitePreprocess } from "@sveltejs/kit/vite";
    import adapter from "@sveltejs/adapter-node";

    const config = {
        preprocess: vitePreprocess(),
        kit: {
            adapter: adapter(),
        },
    };

    export default config;
    ```

    Make sure to install the corresponding adapter package. For example, if using `@sveltejs/adapter-node`:

    ```
    npm install @sveltejs/adapter-node
    ```

    Don't forget to remove `@sveltejs/adapter-auto` from `package.json` if you're using a specific adapter!

    You can explore other official and community adapters in the SvelteKit documentation to find the one that suits your deployment needs.

4. Deploy the built files to your chosen platform if you want to share your Discord Activity with others (Discord Proxy).

5. Enjoy your Discord Activity powered by SvelteKit and GameMaker HTML5!

Remember to choose an adapter that matches your deployment platform and follow the specific deployment instructions for that platform.

## Example: Brick Breaker Game

This template includes a sample Brick Breaker game built with GameMaker to demonstrate how to integrate a GameMaker HTML5 build with SvelteKit. The game files are in the `static/html5game` folder.

Feel free to replace the example game with your own GameMaker HTML5 export to showcase your Discord Activity.

## Contributing

Contributions are welcome! If you find any bugs or have suggestions for improvement, please open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

---

In the words of Todd Howard, it just works.
