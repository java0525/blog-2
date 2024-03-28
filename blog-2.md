# Eleventy Essentials: From Zero to Hero with Project Setup, Layouts, and Styling

## Introduction

In the realm of static site generators, Eleventy (also known as 11ty) emerges as a flexible and straightforward option, making it a favored choice for developers looking to create fast, accessible websites without the overhead of complex configurations. This guide aims to walk you through the initial steps of setting up a new Eleventy project, designing reusable layouts, and effectively managing images and styles. Whether you are building a personal blog, a portfolio, or a small business site, these foundational skills will serve as the cornerstone of your Eleventy journey.

## Setting Up Your Eleventy Project

### Prerequisites

- Basic knowledge of HTML and CSS
- Node.js and npm installed on your machine

### Step 1: Project Initialization

1. Create a new directory for your project and navigate into it:
   ```bash
   mkdir my-eleventy-project && cd my-eleventy-project
   ```
2. Initialize a new npm project:
   ```bash
   npm init -y
   ```
3. Install Eleventy:
   ```bash
   npm install --save-dev @11ty/eleventy
   ```

### Step 2: Running Eleventy

- Start Eleventy in serve mode, which will watch your files for changes and refresh the browser automatically:
  ```bash
  npx eleventy --serve
  ```
- By default, Eleventy serves your site at `http://localhost:8080`.

![start_image](https://github.com/java0525/blog-2/blob/main/start.png)

## Creating Layouts

Layouts are templates that allow you to define a consistent structure for your pages, such as headers, footers, and navigation bars, without repeating code.

### Step 1: Defining a Base Layout

1. Create a `_includes` directory in your project root. This is where your layout files will live.
2. Inside `_includes`, create a file named `base.njk` (for Nunjucks, a templating language supported by Eleventy). This will be your base layout.

Here's a simple example of what `base.njk` might contain:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{ title }}</title>
    <link rel="stylesheet" href="/css/global.css">
</head>
<body>
    <header>
        <!-- Your site's header -->
    </header>

    <main>
        {{ content | safe }}
    </main>

    <footer>
        <!-- Your site's footer -->
    </footer>
</body>
</html>
```

### Step 2: Using the Layout in Pages

- When creating a new page (e.g., `index.html`), you can specify this layout at the top of your file using Front Matter:

  ```html
  ---
  layout: base.njk
  title: Home Page
  ---
  <p>Welcome to my Eleventy site!</p>
  ```

## Managing Styles and Images

### Global CSS Styles

- Create a `css` directory in your project root for your CSS files.
- For global styles, you might have a `global.css` file in this directory with site-wide styles.
- Reference this CSS file in your base layout, as shown in the `base.njk` example above.

### Page Specific CSS Styles

- For page-specific styles, create a CSS file corresponding to the page (e.g., `about.css` for `about.html`).
- Include a reference to this CSS file in the Front Matter of your page, and modify your base layout to conditionally load this file if it exists.

### Using Images

- Store your images in an `images` directory at the root of your project.
- Reference images in your HTML using relative paths, e.g., `<img src="/images/my-image.jpg" alt="Description">`.

![insert_image](https://github.com/java0525/blog-2/blob/main/image.png)

## Conclusion

You've now laid the foundation for your Eleventy project, equipped with a reusable layout system and a structured approach to managing styles and images. This setup not only streamlines your development process but also ensures that your site remains maintainable and scalable as it grows.

As you become more comfortable with Eleventy, explore its extensive features, such as data files, collections, and plugins, to further enhance your site. The flexibility and simplicity of Eleventy make it a powerful tool in your web development arsenal, enabling you to create fast, efficient, and accessible websites with ease.
Happy coding!
