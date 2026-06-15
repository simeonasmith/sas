# Simeon A. Smith — Static Website + GitHub Pages + Decap CMS

This is a static essay website designed to look like a pastel blue-grey cousin of the Financial Times.

It uses:

- **GitHub Pages** for free static hosting
- **Jekyll** to generate article pages automatically
- **Decap CMS** for a private browser-based editor at `/admin`
- **Markdown files** for essays

## What you get

- Public homepage with newspaper-style article cards
- Individual article pages
- Archive page
- About page
- Private admin editor
- Articles stored as Markdown files in `_posts`
- Uploaded images/files stored in `assets/uploads`

## First setup

### 1. Create a GitHub repository

Create a new GitHub repository, for example:

`simeon-essays`

Upload all these files into it.

### 2. Edit `admin/config.yml`

Replace:

```yml
repo: YOUR-GITHUB-USERNAME/YOUR-REPOSITORY-NAME
```

with your actual GitHub username and repository name, for example:

```yml
repo: simeonasmith/simeon-essays
```

Also update:

```yml
site_url: "https://YOUR-GITHUB-USERNAME.github.io/YOUR-REPOSITORY-NAME"
display_url: "https://YOUR-GITHUB-USERNAME.github.io/YOUR-REPOSITORY-NAME"
```

For example:

```yml
site_url: "https://simeonasmith.github.io/simeon-essays"
display_url: "https://simeonasmith.github.io/simeon-essays"
```

### 3. Turn on GitHub Pages

In the repository:

Settings → Pages → Build and deployment

Choose:

- Source: **Deploy from a branch**
- Branch: **main**
- Folder: **/root**

Save.

Your site should appear at:

`https://YOUR-GITHUB-USERNAME.github.io/YOUR-REPOSITORY-NAME`

### 4. Enable Decap CMS login

Decap CMS needs GitHub authentication. The simplest route is to use Netlify for hosting because it has Identity built in. But if you want to stay purely on GitHub Pages, you need a small OAuth gateway.

The easiest practical options are:

1. Host the same repository on **Netlify** instead of GitHub Pages and enable Netlify Identity/Git Gateway.
2. Use a GitHub OAuth gateway for Decap CMS.
3. Edit articles directly in GitHub if you do not want to configure authentication yet.

For the most painless setup, use **Netlify + Decap CMS**. The site is still static; Netlify just handles the login.

## Using the private desk

Once authentication is configured, go to:

`/admin`

There you can:

- create essays
- edit essays
- delete essays
- upload images/files
- save drafts
- publish pieces

## How article filenames work

Decap creates Markdown files in `_posts` using:

`YYYY-MM-DD-title-with-dashes.md`

Jekyll then turns them into public article pages using the title-based URL style:

`/title-with-dashes/`

## Local preview, optional

If you have Ruby/Jekyll installed:

```bash
bundle install
bundle exec jekyll serve
```

Then open:

`http://localhost:4000`
