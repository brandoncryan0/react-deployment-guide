# Verify Your Project

Before publishing your website, make sure the project works correctly on your computer.

Deploying a project does not fix errors in the code. Testing the project locally first makes deployment problems easier to identify.

## Open Your Project

Open PowerShell and move into your React project folder.

For example:

```bash
cd my-react-project
```

Your project should contain files similar to:

```text
src/
public/
package.json
vite.config.js
```

## Install Dependencies

Run:

```bash
npm install
```

This installs the packages listed in your project's `package.json` file.

If the installation finishes without an error, continue to the next step.

## Start the Development Server

Run:

```bash
npm run dev
```

Vite will display a local address similar to:

```text
http://localhost:5173/
```

Open the address in your browser.

## Check the Website

Before continuing, verify that:

- the homepage loads correctly
- navigation links work
- images appear
- buttons and interactive features work
- text and layouts display correctly
- the website works at different browser widths

If something is broken locally, fix it before attempting to deploy the website.

## Test the Production Build

The development server is not the version that will be published online.

Create a production build by running:

```bash
npm run build
```

If the build succeeds, Vite creates a folder named:

```text
dist/
```

The `dist` folder contains the optimized files that will be used for the production website.

## Preview the Production Build

You can test the production version locally by running:

```bash
npm run preview
```

Vite will display another local address.

Open it in your browser and check the website again.

Pay particular attention to:

- navigation
- images
- page routes
- interactive features
- browser console errors

## If the Build Fails

Do not continue to deployment if `npm run build` reports an error.

Read the terminal output and fix the reported problem first. A project that does not build locally will usually fail when a hosting service attempts to build it.

## Next Step

Once the development version and production build both work correctly, continue to [Set Up Git](git-setup.md).
