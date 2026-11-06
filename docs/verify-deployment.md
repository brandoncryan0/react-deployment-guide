# Verify the Deployment

A successful deployment means that Vercel was able to build and publish the project.

It does not guarantee that every part of the website works correctly.

Before sharing the website, test the production version carefully.

## Open the Production Website

Open the public Vercel URL.

It will usually look similar to:

```text
https://your-project.vercel.app
```

Do not test only the local development version.

The purpose of this step is to verify the version that users will actually visit.

## Check the Homepage

Confirm that:

- the page loads without errors
- headings and text appear correctly
- fonts load correctly
- colors and spacing match the local version
- images appear
- buttons work
- no important content is missing

If the production site looks different from the local version, investigate before continuing.

## Test Navigation

Click every navigation link.

Verify that:

- internal links open the correct page
- external links open the expected website
- buttons navigate correctly
- project or detail pages load
- the browser back button works as expected

Do not assume that a link works just because it worked locally.

## Test Direct Page URLs

If your website uses multiple routes, open those routes directly in the browser.

For example:

```text
https://your-project.vercel.app/about
```

or:

```text
https://your-project.vercel.app/projects/example
```

Then refresh the browser.

If the route returns a 404 error after refreshing, your application may need additional configuration for client-side routing.

This is especially important for React applications that use React Router.

## Check Images and Other Assets

Verify that:

- images load
- icons appear
- downloadable files work
- fonts load
- image paths are correct
- filenames use the correct capitalization

A path that works on your computer may fail in production if the capitalization does not match the actual filename.

For example:

```text
HeroImage.png
```

and:

```text
heroimage.png
```

may be treated as different filenames in a production environment.

## Test Interactive Features

If your website contains interactive elements, test them individually.

Examples include:

- forms
- menus
- dropdowns
- buttons
- search
- animations
- filters
- calculators
- visualizations

Confirm that each feature behaves the same way it did during local testing.

## Test Different Screen Sizes

Resize your browser window and check the layout at different widths.

At minimum, check:

- desktop
- tablet-sized width
- mobile-sized width

Look for problems such as:

- text extending off the screen
- overlapping elements
- images that are too large
- buttons that are difficult to use
- navigation that does not fit
- horizontal scrolling

You can also use your browser's developer tools to simulate different devices.

## Check the Browser Console

Open your browser's developer tools.

In most browsers, you can press:

```text
F12
```

or right-click the page and select:

```text
Inspect
```

Open the **Console** tab.

Look for errors shown in red.

Warnings do not always indicate a serious problem, but errors should be investigated.

Common production errors include:

- missing files
- failed API requests
- incorrect asset paths
- JavaScript exceptions
- missing environment variables

## Check Network Requests

Open the **Network** tab in the browser developer tools.

Refresh the page.

Look for failed requests.

A failed request may appear with a status code such as:

```text
404
```

or:

```text
500
```

A `404` usually means that a requested resource could not be found.

A `500` generally indicates a server-side problem.

## Test in Another Browser

If possible, open the website in at least one additional browser.

For example:

- Chrome
- Edge
- Firefox

A site that works in one browser may still have compatibility problems in another.

## Test in a Private Window

Open the production website in an incognito or private browsing window.

This can help identify issues caused by:

- cached files
- saved login sessions
- browser extensions
- previously stored site data

It also provides a better approximation of what a first-time visitor may experience.

## Verify the Page Title

Check the browser tab.

The page should display a meaningful title rather than a default such as:

```text
Vite + React
```

A better title might be:

```text
Brandon Cryan | Portfolio
```

or the appropriate name for your project.

## Verify the Page Description

If your website includes metadata, confirm that the description accurately describes the site.

This information may be used by search engines and social platforms.

For example:

```html
<meta
  name="description"
  content="Portfolio featuring software development, mathematics, and technical communication projects."
/>
```

## Check for Broken Links

Open important links and confirm that they lead to the expected destination.

Pay particular attention to:

- GitHub repositories
- LinkedIn profiles
- resume files
- project demos
- downloadable documents

Broken links can make an otherwise complete website appear unfinished.

## Production Verification Checklist

Before considering the deployment complete, verify the following:

- [ ] homepage loads correctly
- [ ] navigation works
- [ ] direct page URLs work
- [ ] page refreshes do not cause unexpected 404 errors
- [ ] images and assets load
- [ ] interactive features work
- [ ] layout works on desktop
- [ ] layout works on mobile
- [ ] browser console contains no major errors
- [ ] important network requests succeed
- [ ] external links work
- [ ] page title is correct
- [ ] page description is correct
- [ ] production URL is correct

## If You Find a Problem

Do not edit files directly through Vercel.

Return to your local project and make the correction there.

The general workflow is:

```text
Find production problem
        ↓
Reproduce locally
        ↓
Edit the project
        ↓
Test locally
        ↓
Commit the fix
        ↓
Push to GitHub
        ↓
Vercel redeploys
        ↓
Test production again
```

Keeping changes in the Git workflow ensures that your repository remains the source of truth for the website.

## Next Step

Once the production website passes your checks, continue to [Update Your Website](updating-site.md).
