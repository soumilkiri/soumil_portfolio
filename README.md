# Soumil Khatri - Personal Portfolio Website

A modern, professional, and responsive personal portfolio website crafted for **Soumil Khatri**, B.Tech CSE student at **JECRC University, Jaipur**.

---

## 🌟 Highlights & Features

- **No Fake Information**: Follows an authentic and honest student approach. All skills, projects, and certifications are presented with genuine "learning in progress" messaging and clean editable placeholders.
- **8 Dedicated Sections**:
  1. **Home**: Hero section with name, "B.Tech CSE Student", professional introduction, CTA buttons, and student summary card.
  2. **About Me**: Professional introduction strictly based on your verified background and goals.
  3. **Education**: Detailed university card highlighting your B.Tech Computer Science degree at JECRC University, Jaipur.
  4. **Skills**: Features the prompt message: *"Currently developing my technical skills through my Computer Science education and practical learning."* with customizable learning roadmap slots.
  5. **Projects**: Features the prompt message: *"Projects will be added as I build and complete them."* with future-ready project cards.
  6. **Certifications & Achievements**: Features the prompt message: *"Certifications and achievements will be added as I earn them."* with future milestone cards.
  7. **Career Goal**: Dedicated spotlight on your mission: *"To become a good web developer by continuously learning, developing strong technical skills and gaining practical experience."*
  8. **Contact**: Clean contact section with masked email (`soum****ri@gmail.com`), masked mobile (`+91 98879 *****`), direct email button (`mailto:soumilkiri@gmail.com`), and interactive contact form.
- **Theme Toggle**: Built-in Dark and Light mode switcher with automatic preference saving (`localStorage`).
- **Responsive Navigation**: Smooth mobile drawer navigation, scroll spy (highlights current active section), and back-to-top button.
- **100% Self-Contained & Resilient**: Styles and interactive scripts are embedded directly inside `index.html` alongside external fallbacks (`./css/style.css` & `./js/script.js`). This guarantees that your site will **never show an unstyled white screen** regardless of deployment environment or path differences.

---

## 📁 Project Structure

```
My First Portfolio/
├── index.html         # Main semantic HTML structure (self-contained with embedded styles & scripts)
├── .nojekyll          # Disables Jekyll on GitHub Pages so all static assets load properly
├── vercel.json        # Configuration file for clean routing on Vercel
├── css/
│   └── style.css      # Standalone stylesheet (colors, dark/light themes, animations, responsive design)
├── js/
│   └── script.js      # Standalone JavaScript (theme toggle, mobile menu, scroll spy, contact form)
└── README.md          # Project documentation and deployment guide
```

---

## 🚀 How to Open and View Locally

You can view your website immediately in any web browser:

1. **Direct Double-Click**:
   - Open your project folder: `d:\Soumil Khatri\My First Portfolio`.
   - Double-click `index.html` to open it in your default web browser (Chrome, Edge, Firefox, Brave, etc.).

2. **Using VS Code Live Server (Optional)**:
   - Open the folder in VS Code.
   - Right-click `index.html` and click **"Open with Live Server"**.

---

## 🌐 How to Deploy to GitHub Pages & Vercel (Fixing the "White Screen" Issue)

### Why Did the White Screen & Raw Text Happen?
When deploying static sites to GitHub Pages or Vercel, the "white screen with unstyled text" happens for three common reasons:
1. **Root Folder Mismatch**: If you upload the parent folder `My First Portfolio` to GitHub instead of uploading the files *inside* it, `index.html` is located at `/My First Portfolio/index.html` instead of the root `/index.html`. GitHub Pages and Vercel look for `index.html` at the root!
2. **Missing Asset Folders**: If you drag-and-dropped only `index.html` into GitHub's web interface, the `css/` and `js/` folders were missing on the server, resulting in a 404 for styles.
3. **Subpath URL Resolution**: On GitHub Pages (`https://username.github.io/repo-name`), without a trailing slash, relative paths like `css/style.css` can resolve to the wrong parent URL.

### How We Fixed It:
1. **Self-Contained `index.html`**: The full CSS and JavaScript have been embedded directly inside `index.html` in addition to relative links (`./css/style.css` and `./js/script.js`). Even if only `index.html` is uploaded, **it will always render with 100% complete styling and full interactivity!**
2. **Progressive Enhancement for Animations**: Content is visible by default (`opacity: 1`), ensuring content is never hidden if JavaScript loading is delayed.
3. **Added `.nojekyll`**: Tells GitHub Pages to skip Jekyll processing and serve files directly.
4. **Added `vercel.json`**: Ensures Vercel serves the static site with clean URLs.

---

### Step-by-Step Deployment Instructions

#### A. Deploying on GitHub Pages

1. **Check Your GitHub Repository Root**:
   Make sure the files inside your GitHub repository look like this (at the ROOT level, NOT inside a folder):
   ```
   your-repo/
   ├── index.html    <-- MUST be at the root!
   ├── .nojekyll
   ├── vercel.json
   ├── css/
   │   └── style.css
   ├── js/
   │   └── script.js
   └── README.md
   ```
2. **Enable GitHub Pages**:
   - Go to your repository on **GitHub.com**.
   - Click on **Settings** (top navigation tab).
   - In the left sidebar, click on **Pages**.
   - Under **Build and deployment** > **Source**, choose **Deploy from a branch**.
   - Under **Branch**, select **`main`** (or `master`) and set the folder to **`/ (root)`**.
   - Click **Save**.
3. **Wait 1-2 Minutes**:
   - GitHub Pages will build your site. Refresh the Pages tab and click your live link (e.g., `https://soumil.github.io/your-repo/`).

---

#### B. Deploying on Vercel

1. Go to [vercel.com](https://vercel.com) and log in with your GitHub account.
2. Click **"Add New..."** > **"Project"**.
3. Select your GitHub portfolio repository and click **Import**.
4. In the **Configure Project** screen:
   - **Framework Preset**: Select **Other**.
   - **Root Directory**: Keep as `./` (or if your GitHub repo contains a nested folder `My First Portfolio`, click *Edit* and select `My First Portfolio`).
   - **Build Command**: Leave empty.
   - **Output Directory**: Leave empty.
5. Click **Deploy**.
6. In ~15 seconds, your site will be live with full styles, dark/light theme, and animations!

---

## ✏️ How to Edit Your Personal Details (When Ready)

All sections in [`index.html`](file:///d:/Soumil%20Khatri/My%20First%20Portfolio/index.html) contain clear `<!-- EDITABLE PLACEHOLDER -->` comments so you can easily locate and update them:

### 1. Adding a Personal Profile Photo
In [`index.html`](file:///d:/Soumil%20Khatri/My%20First%20Portfolio/index.html) around line 2090 (in the Hero card):
- Create a folder named `assets/` and place your photo there (e.g., `assets/soumil.jpg`).
- Replace the `.avatar-monogram` `<div>` with:
  ```html
  <img src="assets/soumil.jpg" alt="Soumil Khatri" style="width:100%; height:100%; border-radius:50%; object-fit:cover;">
  ```

### 2. Adding Your Skills
In [`index.html`](file:///d:/Soumil%20Khatri/My%20First%20Portfolio/index.html) under `<section id="skills">`:
- Look for the `<div class="skill-chips-wrap">` containers.
- Add or replace skill chips as you learn technologies (e.g., `C++`, `Python`, `HTML5`, `CSS3`, `JavaScript`, `React`, `Git`).

### 3. Adding Your Completed Projects
In [`index.html`](file:///d:/Soumil%20Khatri/My%20First%20Portfolio/index.html) under `<section id="projects">`:
- Find `<div class="project-card placeholder-card">`.
- Update the project title, description, tags, and add direct links to your GitHub repositories or live demos.

### 4. Adding Certifications
In [`index.html`](file:///d:/Soumil%20Khatri/My%20First%20Portfolio/index.html) under `<section id="certifications">`:
- Find `<div class="cert-card placeholder-cert">`.
- Update with the certification title, issuing organization (e.g., Coursera, HackerRank, University), and completion date.
