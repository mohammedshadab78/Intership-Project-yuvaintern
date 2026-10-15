# Web Development Internship — Onboarding Task

**Repository:** [Intership-Project-yuvaintern](https://github.com/mohammedshadab78/Intership-Project-yuvaintern)  
**Role:** Web Development Intern  
**Environment:** Windows 10/11  
**Tools:** Visual Studio Code, Node.js, npm, React, Vite, Git, GitHub

## 1. Objective

Set up the local web development environment, create a React application, verify that it runs, and publish the project to GitHub. This onboarding task introduces the tools and workflow used for future internship assignments.

## 2. Install the required tools

Install these tools:

- [Visual Studio Code](https://code.visualstudio.com/download) — code editor
- [Node.js LTS](https://nodejs.org/en/download) — JavaScript runtime; npm is included
- [Git for Windows](https://git-scm.com/install/windows) — source control
- A modern browser such as Chrome or Edge — test the application

Open **Command Prompt (CMD)** and verify the installations:

```cmd
node -v
npm -v
git --version
code --version
```

Each command should return a version. If `code` is not recognized, open the project from VS Code using **File → Open Folder**.

## 3. Create a React project

In CMD, run the commands one by one:

```cmd
cd /d "%USERPROFILE%\Documents"
if not exist internship-projects mkdir internship-projects
cd internship-projects
npm create vite@latest my-react-app -- --template react
cd my-react-app
npm install
code .
```

If the project already exists, skip the project-creation command and navigate to its existing directory instead.

## 4. Run the app

From the root of the React project, run:

```cmd
npm run dev
```

Open the local URL shown in the terminal, usually `http://localhost:5173/`. Keep the terminal running while testing the page. Stop the server with **Ctrl+C**.

## 5. Example Hello World React component

Open `src/App.jsx` and replace its contents with:

```jsx
import './App.css'

function App() {
  return (
    <main className="container">
      <h1>Hello World! 👋</h1>
      <h2>Welcome to React</h2>
      <p>My web development internship starts here.</p>
      <button onClick={() => alert('React is working!')}>
        Click Me
      </button>
    </main>
  )
}

export default App
```

Open `src/App.css` and use:

```css
.container {
  text-align: center;
  margin: 100px auto 0;
  padding: 24px;
  font-family: Arial, sans-serif;
}

h1 {
  color: #2563eb;
}

p {
  font-size: 18px;
  color: #555;
}

button {
  background: #2563eb;
  color: white;
  padding: 12px 24px;
  border: 0;
  border-radius: 8px;
  cursor: pointer;
}

button:hover {
  background: #1d4ed8;
}
```

The Vite React template normally imports `App.css` from `App.jsx` and renders `App` from `src/main.jsx`. Keep the generated `main.jsx` and `package.json` unless you have a specific reason to change them.

Verify React packages:

```cmd
npm list react react-dom
```

Verify the production build:

```cmd
npm run build
```

A successful build creates a `dist` folder.

## 6. Push the project to the internship GitHub repository

**Target repository:**  
https://github.com/mohammedshadab78/Intership-Project-yuvaintern

First, change into the folder containing the project files. Adjust the path to match where your project is saved:

```cmd
cd /d "%USERPROFILE%\Documents\internship-projects\my-react-app"
```

Check which repository is configured:

```cmd
git status
git remote -v
```

If this folder is not yet a Git repository, initialize and commit:

```cmd
git init
git add .
git status
git commit -m "Initial React internship project"
git branch -M main
```

Configure the target remote. This command works whether an `origin` already exists or not:

```cmd
git remote get-url origin
```

If the command reports a URL, update it:

```cmd
git remote set-url origin https://github.com/mohammedshadab78/Intership-Project-yuvaintern.git
```

If no `origin` exists, add one instead:

```cmd
git remote add origin https://github.com/mohammedshadab78/Intership-Project-yuvaintern.git
```

Then push:

```cmd
git push -u origin main
```

If Git says **nothing to commit**, a commit already exists; continue with the branch, remote and push steps. If Git asks you to authenticate, complete the GitHub sign-in prompt.

**Important:** The GitHub repository should be empty for the simplest first push. If it already contains a README or other commits, do not force-push; inspect and reconcile the histories first.

## 7. GitHub safety and project hygiene

- Keep `node_modules/` out of Git; npm recreates it using `npm install`.
- Never commit `.env` files, passwords, API keys or other secrets.
- Check `git status` before committing.
- Keep meaningful commit messages.
- Use the repository README to record the project's purpose and setup commands.

## 8. Basic team workflow

For a future task, create a feature branch:

```cmd
git switch -c feature/update-homepage
```

After making changes:

```cmd
git add .
git commit -m "Improve homepage"
git push -u origin feature/update-homepage
```

Then open a pull request on GitHub to request review before merging, following the mentor's instructions.

## 9. Completion checklist

- [ ] VS Code, Node.js, npm, Git and browser installed
- [ ] Versions verified in CMD
- [ ] React project created with Vite
- [ ] Hello World page displayed in browser
- [ ] Button interaction tested
- [ ] `npm run build` completed successfully
- [ ] Git repository initialized and commit created
- [ ] Code pushed to the correct GitHub repository
- [ ] README and project structure reviewed
- [ ] No secrets or `node_modules` committed
- [ ] Team workflow and pull requests understood

## 10. Learning resources

- [MDN Web Development](https://developer.mozilla.org/en-US/docs/Learn_web_development)
- [React documentation](https://react.dev/learn)
- [Vite guide](https://vite.dev/guide/)
- [Git documentation](https://git-scm.com/doc)
- [GitHub documentation](https://docs.github.com/en)

## Outcome

On completing this task, the development environment should be ready for React work, a local application should run and build, and the code should be available in the internship GitHub repository.

**Status note:** This document describes the intended steps and expected checks. Mark the checklist only after verifying each item on your machine.
