# NPM vs. NPX

## NPM (Node Package Manager)

NPM is the standard package manager for Node.js that allows you to install and manage JavaScript packages. It primarily:

- Installs packages locally in your project's `node_modules` folder
- Installs packages globally on your machine
- Manages dependencies listed in your `package.json` file
- Runs scripts defined in your `package.json`

When you run `npm install express`, it downloads the Express package and saves it to your project.

## NPX (Node Package Executor)

NPX is a package runner tool that comes bundled with NPM (since version 5.2.0) that makes it easier to execute packages. It primarily:

- Executes packages without having to install them first
- Runs locally installed packages directly without path references
- Automatically finds and runs packages from your local `node_modules` folder
- Temporarily downloads and executes packages if they're not installed

## Key Differences

1. **Installation vs. Execution**:

   - NPM: Focuses on installing packages
   - NPX: Focuses on executing packages

2. **Storage**:

   - NPM: Permanently installs packages
   - NPX: Can run packages without permanent installation

3. **Common Use Cases**:
   - NPM: Managing project dependencies
   - NPX: Running one-off commands or tools

## Examples

**NPM**:

```bash
# Install a package
npm install prettier

# Install a global package
npm install -g typescript

# Run a script from package.json
npm run build
```

**NPX**:

```bash
# Run a package without installing
npx create-react-app my-app

# Run a specific version once
npx cowsay@2.0.0 "Hello!"

# Execute a locally installed package easily
npx prettier --write .
```

NPX is particularly useful for packages you only need occasionally or for one-time use, while NPM is essential for managing the packages your project depends on.
