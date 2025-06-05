# Akhila Kudupudi's Portfolio – Setup & Deployment Guide

This repo documents how I built and deployed my React-based developer portfolio using GitHub Pages.

---

## Akhila Kudupudi – Portfolio Website

A responsive, modern portfolio built using **React** and **Tailwind CSS**, featuring projects, publications, resume, and more. Deployed on **GitHub Pages**.


---

##  Technologies Used

- React (with `create-react-app`)
- Tailwind CSS
- JSX Components
- GitHub Pages for deployment
- Custom Assets: images, resume (PDF), background video

---

## Project Structure Overview
"
my-portfolio/
├── public/
│   ├── your-photo.jpg
│   ├── Resume_AkhilaKudupudi_Portfolio.pdf
│   ├── real-dust-particles-black-background.mp4
│   ├── [logos and images used across pages]
├── src/
│   ├── components/
│   │   ├── About.js
│   │   ├── Experience.js
│   │   ├── Projects.js
│   │   ├── Skills.js
│   │   ├── Publications.js
│   │   ├── Resume.js
│   │   ├── Contact.js
│   │   └── Navbar.js
│   ├── App.js
│   └── index.js
"

---

##  Step 1: Create the React App

```bash
npx create-react-app my-portfolio
cd my-portfolio
```

---

## Step 2: Install Tailwind CSS

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

### Update `tailwind.config.js`:

```js
content: ["./src/**/*.{js,jsx,ts,tsx}"]
```

### Update `src/index.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

---

## Step 3: Build Sections in `src/components/`

Create the following components inside the `src/components/` folder:

- `Navbar.js`: Navigation bar with smooth scroll links to all sections.
- `About.js`: Brief intro, background image, and profile.
- `Skills.js`: Categorized technical skills with logos.
- `Experience.js`: Job roles, tools, and achievements.
- `Projects.js`: Portfolio projects with images and GitHub links.
- `Publications.js`: IEEE paper with abstract, links, and authors.
- `Resume.js`: PDF resume viewer and download option.
- `Contact.js`: Contact info or form.

Each file is a standalone React component styled with Tailwind.

---

## Step 4: Add Assets to `public/`

Place the following in the `public/` folder:

- Resume PDF → `Resume_AkhilaKudupudi_Portfolio.pdf`
- Background video → `real-dust-particles-black-background.mp4`
- Company and project images → `TCS.jpeg`, `woolworths.jpeg`, etc.
- Tool logos → `python.webp`, `tableau.png`, etc.

### Reference assets in JSX like this:

```jsx
<img src={`${process.env.PUBLIC_URL}/TCS.jpeg`} alt="TCS Logo" />
<video src={`${process.env.PUBLIC_URL}/real-dust-particles-black-background.mp4`} autoPlay loop muted />
```

---

## Step 5: Update Routing in `App.js`

Import and render all the components inside `App.js`:

```jsx
import Navbar from './components/Navbar';
import About from './components/About';
import Skills from './components/Skills';
import Experience from './components/Experience';
import Projects from './components/Projects';
import Publications from './components/Publications';
import Resume from './components/Resume';
import Contact from './components/Contact';

function App() {
  return (
    <div>
      <Navbar />
      <About />
      <Skills />
      <Experience />
      <Projects />
      <Publications />
      <Resume />
      <Contact />
    </div>
  );
}
```

---

## Step 6: Test Locally

Run the development server:

```bash
npm start
```

Check that:

- Images, logos, and videos display correctly
- Resume PDF loads inside iframe and downloads
- Smooth scrolling between sections
- Responsive layout on mobile and desktop

---

## Step 7: Deploy to GitHub Pages

### 1. Add homepage in `package.json`:

```json
"homepage": "https://akhila-kudupudi.github.io/akhila-portfolio"
```

### 2. Install `gh-pages`:

```bash
npm install --save-dev gh-pages
```

### 3. Add deployment scripts to `package.json`:

```json
"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d build"
}
```

### 4. Deploy 

```bash
npm run deploy
```

This will push the production build to GitHub Pages.

---

## Common Issues & Fixes

-  **Images not loading?**  
  Use public asset paths:
  ```jsx
  src={`${process.env.PUBLIC_URL}/file-name`}
  ```

-  **Resume PDF not visible?**  
  Make sure it's placed inside the `public/` folder.

-  **404 on GitHub Pages?**  
  - Check `homepage` field in `package.json`
  - Confirm you ran `npm run deploy` after pushing code
  - Your repo should be public

---

## 📚 Summary

| Feature         | Tech Used              |
|----------------|------------------------|
| Framework       | React                  |
| Styling         | Tailwind CSS           |
| Hosting         | GitHub Pages           |
| Deployment Tool | `gh-pages` npm package |
| Asset Storage   | Static files in `public/` |

---

## 🧑‍💻 Author

👩‍💻 Built with ❤️ by **Akhila Kudupudi**  
📧 akhila06121999@gmail.com  
🔗 [GitHub](https://github.com/Akhila-kudupudi)

---

Feel free to fork and customize this template for your own portfolio!
