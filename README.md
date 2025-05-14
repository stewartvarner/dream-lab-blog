# Dream Lab Blog Template

This repository (aka. a repo; a central storage for your project's files, folders, and version history) has all the files and instructions to build a basic personal website with an about me page, a link to a CV [PDF], and a simple blog with the [Eleventy](https://www.11ty.dev/) site generator (using the [v3.0 release](https://github.com/11ty/eleventy/releases/tag/v3.0.0)).

This project will teach you how to use multiple functions with GitHub to create a website, including [GitHub Pages](https://pages.github.com/) which hosts your static site for free and [GitHub Codespaces](https://github.com/features/codespaces) which combines an explorer, code editor, and terminal to allow you to make updates to "push" and "pull" from your repository (from your local copy to the remote version). 

I recommend using Google Chrome for this exercise so you can easily use the Developer tools like "View Source" and "Inspect Elements".

## Getting Started

1. [Create a GitHub account](https://github.com/signup) if you do not already have one. (NOTE: You will want to pick a professional username because it will be in all of your URLs)
2. Navigate back to [this repository](https://github.com/Makeademic/dream-lab-blog/) and click the green button that says "Use this template" and then "Create a new repository"
3. Type a name for your new repository (NOTE: lowercase and no spaces is best for URLs with hyphens or underscores separating each word)
4. Select "Public" repository visibility and you only need to include the "main" branch (We will build the gh-pages branch in a later step)
5. Click "Create repository from template"

**Review**
So far, what we have done is created a copy of a public project on our individual accounts so that we can edit and make changes to the files

## Setting Up Your Project in GitHub Codespaces

>Typically coders using GitHub use their favorite text editor like [Sublime Text](https://www.sublimetext.com/), [Atom](https://atom-editor.cc/), or [Visual Studio Code](https://code.visualstudio.com/), and then use a graphical user interface (GUI) like [GitHub Desktop](https://github.com/apps/desktop) or their command-line interface (CLI) like Terminal to push and pull changes to their project. GitHub created Codespaces to allow you to do both of those things right in the browser without having to download software applications (so you can do all of this on your iPad if you want!)

1. On your repository's homepage, click the green "Code" button and switch from the "Local" to the "Codespaces" tab. Then click the green "Create codespace on main" button.
2. This will open up a new tab in your browser and will take some time, so be patient with it. [NOTE: As of authoring this document, GitHub provides 60 free hours of Codespaces every month]
3. You should see the Explorer on the left (this helps you see folder hierarchy), the Editor on the right (this is where you can edit the code), and the Terminal at the bottom (this is where we will provide instructions for building our project). The far left toolbar will let you switch between options: Explorer, Search, Source Control, Run and Debug, Extensions, and GitHub.
4. In the Explorer, navigate to _data/metadata.js and double-click to open the file in the Editor space. Change the title, URL (https://username.github.io/repositoryname), description, and author data.
5. In the Terminal, install dependencies (the needed files for this version of the project) by copying and pasting the code below and then pressing enter/return.
```
npm install
```
6. You should see new lines of text being generated in the Terminal.

## Editing Files in Your Project

Your text files will be in the "content" folder, your assets like images and documents will be in the "public" folder, and your styling will be in the "css" folder. Some file extensions you will want to know are: 
- .html (Hypertext Markup Language (HTML) is the standard markup language for documents designed to be displayed in a web browser)
- .css (Cascading Style Sheets (CSS) is a style sheet language used for specifying the presentation and styling of a document written in a markup language such as HTML)
- .js (JavaScript (JS) is the programming language for creating interactive, dynamic websites)
- .md (Markdown is a lightweight markup language for creating formatted text using a plain-text editor)
- .njk (Nunjucks is a templating language for JavaScript)
- .svg (Scalable Vector Graphics (SVG) is an XML-based vector graphics format for defining two-dimensional graphics, having support for interactivity and animation)
- .jpg (jpg or jpeg, short for Joint Photographic Experts Group, is a compressed image format used for photos)
- .ico (short for icon, this file format is for square icons like the favicon in your browser tab, can be based on a transparent .png (Portable Network Graphics))

1. Navigate in the Explorer to content/index.njk and double-click to edit the file in the Editor
2. Edit line 16 between the opening and closing `<h1>` tags to your preferred heading
3. You can delete the SVG on lines 17-28



* [Want a more generic/detailed getting started guide?](https://www.11ty.dev/docs/getting-started/)

1. Make a directory and navigate to it:

```
mkdir my-blog-name
cd my-blog-name
```

2. Clone this Repository

```
git clone https://github.com/11ty/eleventy-base-blog.git .
```

_Optional:_ Review `eleventy.config.js` and `_data/metadata.js` to configure the site’s options and data.

3. Install dependencies

```
npm install
```

4. Run Eleventy

Generate a production-ready build to the `_site` folder:

```
npx @11ty/eleventy
```

Or build and host on a local development server:

```
npx @11ty/eleventy --serve
```

Or you can run [debug mode](https://www.11ty.dev/docs/debugging/) to see all the internals.

## Features

- Using [Eleventy v3](https://github.com/11ty/eleventy/releases/tag/v3.0.0) with zero-JavaScript output.
	- Content is exclusively pre-rendered (this is a static site).
	- Can easily [deploy to a subfolder without changing any content](https://www.11ty.dev/docs/plugins/html-base/)
	- All URLs are decoupled from the content’s location on the file system.
	- Configure templates via the [Eleventy Data Cascade](https://www.11ty.dev/docs/data-cascade/)
- **Performance focused**: four-hundos Lighthouse score out of the box!
	- _0 Cumulative Layout Shift_
	- _0ms Total Blocking Time_
- Local development live reload provided by [Eleventy Dev Server](https://www.11ty.dev/docs/dev-server/).
- Content-driven [navigation menu](https://www.11ty.dev/docs/plugins/navigation/)
- Fully automated [Image optimization](https://www.11ty.dev/docs/plugins/image/)
	- Zero-JavaScript output.
	- Support for modern image formats automatically (e.g. AVIF and WebP)
	- Processes images on-request during `--serve` for speedy local builds.
	- Prefers `<img>` markup if possible (single image format) but switches automatically to `<picture>` for multiple image formats.
	- Automated `<picture>` syntax markup with `srcset` and optional `sizes`
	- Includes `width`/`height` attributes to avoid [content layout shift](https://web.dev/cls/).
	- Includes `loading="lazy"` for native lazy loading without JavaScript.
	- Includes [`decoding="async"`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/decoding)
	- Images can be co-located with blog post files.
- Per page CSS bundles [via `eleventy-plugin-bundle`](https://github.com/11ty/eleventy-plugin-bundle).
- Built-in [syntax highlighter](https://www.11ty.dev/docs/plugins/syntaxhighlight/) (zero-JavaScript output).
- Draft content: use `draft: true` to mark any template as a draft. Drafts are **only** included during `--serve`/`--watch` and are excluded from full builds. This is driven by the `addPreprocessor` configuration API in `eleventy.config.js`. Schema validator will show an error if non-boolean value is set in data cascade.
- Blog Posts
	- Automated next/previous links
	- Accessible deep links to headings
- Generated Pages
	- Home, Archive, and About pages.
	- [Atom feed included (with easy one-line swap to use RSS or JSON](https://www.11ty.dev/docs/plugins/rss/)
	- `sitemap.xml`
	- Zero-maintenance tag pages ([View on the Demo](https://eleventy-base-blog.netlify.app/tags/))
	- Content not found (404) page

## Demos

- [Netlify](https://eleventy-base-blog.netlify.app/)
- [Vercel](https://demo-base-blog.11ty.dev/)
- [Cloudflare Pages](https://eleventy-base-blog-d2a.pages.dev/)
- [Remix on Glitch](https://glitch.com/~11ty-eleventy-base-blog)
- [GitHub Pages](https://11ty.github.io/eleventy-base-blog/)

## Deploy this to your own site

Deploy this Eleventy site in just a few clicks on these services:

- Read more about [Deploying an Eleventy project](https://www.11ty.dev/docs/deployment/) to the web.
- [Deploy this to **Netlify**](https://app.netlify.com/start/deploy?repository=https://github.com/11ty/eleventy-base-blog)
- [Deploy this to **Vercel**](https://vercel.com/import/project?template=11ty%2Feleventy-base-blog)
- Look in `.github/workflows/gh-pages.yml.sample` for information on [Deploying to **GitHub Pages**](https://www.11ty.dev/docs/deployment/#deploy-an-eleventy-project-to-git-hub-pages).
- [Try it out on **Stackblitz**](https://stackblitz.com/github/11ty/eleventy-base-blog)

### Implementation Notes

- `content/about/index.md` is an example of a content page.
- `content/blog/` has the blog posts but really they can live in any directory. They need only the `posts` tag to be included in the blog posts [collection](https://www.11ty.dev/docs/collections/).
- Use the `eleventyNavigation` key (via the [Eleventy Navigation plugin](https://www.11ty.dev/docs/plugins/navigation/)) in your front matter to add a template to the top level site navigation. This is in use on `content/index.njk` and `content/about/index.md`.
- Content can be in _any template format_ (blog posts needn’t exclusively be markdown, for example). Configure your project’s supported templates in `eleventy.config.js` -> `templateFormats`.
- The `public` folder in your input directory will be copied to the output folder (via `addPassthroughCopy` in the `eleventy.config.js` file). This means `./public/css/*` will live at `./_site/css/*` after your build completes.
- This project uses three [Eleventy Layouts](https://www.11ty.dev/docs/layouts/):
	- `_includes/layouts/base.njk`: the top level HTML structure
	- `_includes/layouts/home.njk`: the home page template (wrapped into `base.njk`)
	- `_includes/layouts/post.njk`: the blog post template (wrapped into `base.njk`)
- `_includes/postslist.njk` is a Nunjucks include and is a reusable component used to display a list of all the posts. `content/index.njk` has an example of how to use it.

#### Content Security Policy

If your site enforces a [Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) (as public-facing sites should), you have a few choices (pick one):

1. In `base.njk`, remove `<style>{% getBundle "css" %}</style>` and uncomment `<link rel="stylesheet" href="{% getBundleFileUrl "css" %}">`
2. Configure the server with the CSP directive `style-src: 'unsafe-inline'` (less secure).
