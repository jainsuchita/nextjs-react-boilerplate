# To start, create a sample project by running the following commands

mkdir <APP_NAME>

cd <APP_NAME>

npm init -y

npm install --save react react-dom next

mkdir pages

# Create gitignore and add this

node_modules

# open the package.json file in the project directory and replace scripts with the following:

```
"scripts": {
  "dev": "next",
  "build": "next build",
  "start": "next start"
}

```

# Now everything is ready. Run the following command to start the dev server:
```
npm run dev

```

# We will see an error page, now start Creating Our First Page
    Create a file named pages/index.js and add the following content:

    ```
    const Index = () => (
        <div>
        <p>Hello Next.js</p>
        </div>
    );

    export default Index;
    ```

`Now if we visit http://localhost:3000 again, we'll see a page with "Hello Next.js"`


