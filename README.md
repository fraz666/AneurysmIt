# AneurysmIt
Web image viewer with "brain aneurysm" sound player

## Development environment
1. Create a Dockerfile containing the required tools

    ```Dockerfile
    FROM alpine:3
    RUN apk update

    # TOOLS
    RUN apk add nodejs npm git

    WORKDIR /app
    ```

2. Build it and name it 
    ```
    docker build -t <dev-env name> .
    ```

3. Run it 
    ```
    docker run --rm -it -p 3000:3000 -v ${PWD}/:/app <dev-env name> ash
    ```

    Thanks to volume binding it's possible to edit the local files and have them updated inside the container.

## Using vite and svelte

1. Scaffolding via a vite template
    ```
    npm create vite@latest src -- --template svelte-ts
    ```

2. Replacing the dev script in package.json
    ```json
    "dev": "vite --host 0.0.0.0 --port 3000"
    ```

3. Starting the dev environment
    ```
    npm i & npm run dev
    ```

