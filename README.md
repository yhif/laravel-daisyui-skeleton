Laravel is the most popular free and open-source PHP web framework that helps you build modern web applications and API's based on a model-view-controller (MVC) programming architecture. 

Check out this guide to learn how to set up a new Laravel project together with Tailwind CSS and the UI components from DaisyUI to enhance your front-end development workflow.

## Install Tailwind CSS with Laravel

Make sure that you have <a href="https://getcomposer.org/" rel="nofollow">Composer</a> and <a href="https://nodejs.org/en/" rel="nofollow">Node.js</a> installed locally on your computer.

Follow the next steps to install Tailwind CSS and DaisyUI with Laravel Mix. 

1. Require the Laravel Installer globally using Composer:

```bash
composer global require laravel/installer
```

Make sure to place the vendor bin directory in your PATH. Here's how you can do it based on each OS:

- macOS: `export PATH="$PATH:$HOME/.composer/vendor/bin"`
- Windows: `set PATH=%PATH%;%USERPROFILE%\AppData\Roaming\Composer\vendor\bin`
- Linux: `export PATH="~/.config/composer/vendor/bin:$PATH"`

2. Create a new project using Laravel's CLI:

```bash
laravel new example-app

cd example-app
```

Start the development server using the following command:

```bash
php artisan serve
```

You can now access the Laravel application on `http://localhost:8000`.

This command will initialize a blank Laravel project that you can get started with.

4. Install Tailwind CSS and DaisyUI using NPM:

```javascript
npm install -D tailwindcss postcss autoprefixer daisyui@latest
```

5. Create a Tailwind CSS config file:

```bash
npx tailwindcss init -p
```

A new `tailwind.config.js` file will be created inside your root folder.

6. Add the view paths and require DaisyUI as a plugin inside `tailwind.config.js`:

```javascript
module.exports = {
    content: [
      "./resources/**/*.blade.php",
      "./resources/**/*.js",
      "./resources/**/*.vue",
      "./node_modules/daisyui/**/*.js"
    ],
    theme: {
      extend: {},
    },
    plugins: [
        require("daisyui")
    ],
  }
```

This will tell the compiler from Tailwind what files to look for to properly apply the classes inside the final CSS file and it will also install the extra plugin options from DaisyUI.

7. Add the directives inside the `./resources/css/app.css` file:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

8. Make sure your compiled CSS and JS is included in the `<head>` then start using Tailwind’s utility classes to style your content.

```javascript
@vite(['resources/css/app.css','resources/js/app.js'])
```

9. Import the DaisyUI JavaScript package inside the `./resources/js/app.js` file to enable the interactive components such as modals, dropdowns, navbars, and more.

```javascript
import 'daisyui';
```

10. Run the build process for Vite using `npm run dev`. Use `npm run build` for production builds.
