# Portfolio Website Deployment on AWS

A personal portfolio website built with HTML and CSS, version-controlled with Git and GitHub, and deployed live using AWS S3 static website hosting.

---

## Project Objective

The objective of this project is to enable students to apply their knowledge of HTML and CSS to build and deploy a personal portfolio website using Git and AWS S3 static hosting.

## Project Information

| Field                | Details                             |
| -------------------- | ----------------------------------- |
| **Project Title**    | Portfolio Website Deployment on AWS |
| **Dataset Source**   | Self-Created Content                |
| **Difficulty Level** | Intermediate                        |
| **Primary Skills**   | HTML, CSS, Git, AWS S3              |

## Problem Description

Create a personal portfolio website and deploy it live using AWS S3 static website hosting.

## Tech Stack

- **HTML5**: page structure and semantic markup
- **CSS3**: styling, layout, and responsive design
- **Git & GitHub**: version control and code hosting
- **AWS S3**: static website hosting

## Project Structure

```
portfolio-website/
├── index.html
├── css/
│   └── style.css
├── images/
└── README.md
```

## Required Steps

### Step 1: Create HTML Structure
Set up `index.html` with the basic skeleton and semantic elements such as `<header>`, `<nav>`, `<main>`, `<section>`, and `<footer>`.

### Step 2: Add Portfolio Sections
Add sections such as About, Skills, Projects, and Contact.

### Step 3: Style Using CSS
Create `css/style.css` and style typography, colors, spacing, navigation, and layout using Flexbox or Grid.

### Step 4: Make Responsive
Add the viewport meta tag and use media queries so the layout adapts to mobile, tablet, and desktop.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### Step 5: Initialize Git Repository

```bash
git init
git add .
git commit -m "Initial commit: portfolio website"
```

### Step 6: Push Code to GitHub

```bash
git remote add origin https://github.com/<your-username>/<your-repo>.git
git branch -M main
git push -u origin main
```

### Step 7: Create AWS S3 Bucket
1. Sign in to the AWS Console and open **S3**.
2. Click **Create bucket** and choose a globally unique name.
3. Select a region.
4. Uncheck *Block all public access* and acknowledge the warning.
5. Click **Create bucket**.

### Step 8: Upload Project Files
1. Open the bucket and click **Upload**.
2. Add `index.html`, the `css/` folder, and the `images/` folder.
3. Click **Upload**.

### Step 9: Enable Static Website Hosting
1. Go to the bucket's **Properties** tab.
2. Under **Static website hosting**, click **Edit** and select **Enable**.
3. Set the index document to `index.html` and save.
4. In the **Permissions** tab, add this bucket policy:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::<your-bucket-name>/*"
    }
  ]
}
```

### Step 10: Test Live Website
Open the bucket website endpoint:

```
http://<your-bucket-name>.s3-website-<region>.amazonaws.com
```

- [ ] All sections load correctly
- [ ] CSS and images display properly
- [ ] Navigation links work
- [ ] Layout is responsive

## Live Demo

- **Website:** `http://<your-bucket-name>.s3-website-<region>.amazonaws.com`
- **GitHub Repository:** `https://github.com/<your-username>/<your-repo>`

## Learning Outcomes

- Build a structured, semantic HTML page
- Style and lay out a page with CSS and make it responsive
- Use Git for version control and push code to GitHub
- Configure an AWS S3 bucket for static website hosting
- Deploy and test a live website

