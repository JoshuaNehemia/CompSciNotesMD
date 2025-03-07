# Introduction to React Structure

Welcome to a video on the **React structure**. After watching this video, you will be able to:
1. Describe the Vite build tool to create React projects.
2. List the steps to create a React project.
3. List the directories and files in a React folder structure.

---

## Vite Build Tool

**Vite** is a build tool that improves the development process for front-end projects. It supports frameworks like React, Angular, and plain JavaScript, as well as any new JavaScript library or system. Vite optimizes development by bundling code only when required, thus speeding up programming and building times.

### Advantages of Vite

- **Faster Build Times**: Bundles code only when needed.
- **Modern JavaScript Handling**: Leverages current browser capabilities.
- **Flexibility**: Works with multiple frameworks and libraries.

---

## Steps to Create a React Project with Vite

To create a project with the Vite tool, follow these steps:

1. **Initialize the Project**:
   ```bash
   npm create vite@latest
   ```
2. **Name the Project**:
   - Enter the desired project name when prompted.

3. **Select Framework**:
   - Use arrow keys to select **React** from the list of frameworks.

4. **Select Language**:
   - Choose **JavaScript** as the scripting language.

5. **Navigate to the Project Directory**:
   ```bash
   cd your_project_name
   ```

6. **Install Dependencies**:
   ```bash
   npm install
   ```

7. **Start the Development Server**:
   ```bash
   npm run dev
   ```

8. **Open the React Application**:
   - Use the provided link and port number to view your React application in a browser.

---

## React Project Folder Structure

After creating a React project with Vite, you will see the following directories and files:

### Main Directories and Files

- **node_modules**: Contains all the dependencies installed through NPM or Yarn.
- **public**: Contains static assets like HTML files, images, and fonts.
  - **index.html**: Serves as the entry point for the React application.
- **src**: Contains the source code for the React application.
  - **App.jsx**: Represents the root component of the React application.
  - **App.css**: Stylesheet for the App component.
  - **main.jsx**: Entry point for the React application, rendering the root component.
  - **index.css**: Global CSS styles.

### Additional Files

- **package.json**: Contains metadata about the project, dependencies, and scripts for running, building, and testing the application.
- **vite.config.js**: Configuration settings for the Vite build tool, including customizing the build process and configuring development server options.
- **.gitignore**: Specifies which files and directories should be ignored by Git version control.
- **README.md**: Provides information about the project, including setup instructions and usage guidelines.
- **.eslintrc.cjs**: Configuration file used by ESLint, a popular linting tool for JavaScript. The `.cjs` extension indicates it is a CommonJS module.

---

## Starting Your React Application

Now that you have created your React project with Vite, you can start building the application by creating more folders and files as needed. Vite's optimized build process ensures efficient development, making it a valuable tool for modern web development.
