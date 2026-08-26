# Top 10 Songs of the Summer

A modern, mobile-friendly Jekyll starter site for a personal ranking of the top 10 songs of the summer. The project is intentionally filled with placeholders so you can add your own song titles, performers, images, reviews, and ratings.

## Included structure

```text
.
├── _config.yml
├── _songs/                  # The 10 Markdown song pages
├── _layouts/
│   ├── default.html         # Shared site shell
│   └── song.html            # Song review template
├── assets/
│   ├── css/style.css        # Responsive visual design
│   ├── js/main.js
│   └── images/              # Add your artwork here
├── index.md                 # Homepage
├── Gemfile
└── README.md
```

## Add or edit a song page

Each file in `_songs/` is a Markdown document with YAML front matter. The front matter controls the data displayed by the layout.

```yaml
---
title: "Your song title"
artist: "Performer name"
rank: 1
image: "/assets/images/song-01.jpg"
image_alt: "Description of the cover or related image"
rating: "★★★★☆"
---
```

After the closing `---`, write your review in normal Markdown. The template is ready for a couple of paragraphs:

```markdown
Your first review paragraph goes here.

Your second review paragraph goes here.
```

### Front matter fields

- `title`: The song title.
- `artist`: The performer or performers.
- `rank`: A number from 1 through 10. The homepage sorts cards using this number.
- `image`: The path to the image inside the repository. Add files to `assets/images/`.
- `image_alt`: A useful accessibility description for the image.
- `rating`: Your rating shown as stars. Use any five-character combination such as `★★★★★`, `★★★★☆`, or `★★★☆☆`.

The starter files are named `song-01.md` through `song-10.md`. Replace their placeholder values without changing the filenames unless you also want to change their URLs.

## Images

Add your images to `assets/images/`, then update the matching `image` field. For example:

```yaml
image: "/assets/images/song-01.jpg"
```

Use images you have permission to publish. Keep image files reasonably optimized for the web. Square images work best with the current design.

## Local preview

Install Ruby and Bundler, then run:

```bash
bundle install
bundle exec jekyll serve --livereload
```

Open the local URL shown in the terminal, normally:

```text
http://localhost:4000
```

Jekyll will rebuild the site as you edit Markdown, layouts, and CSS. Stop the server with `Ctrl+C`.

If you do not want live reload, use:

```bash
bundle exec jekyll serve
```

## Publish through GitHub Pages

1. Create a new GitHub repository.
2. Copy all files from this starter project into the repository.
3. Commit and push the files to the default branch, usually `main`.
4. In GitHub, open **Settings → Pages**.
5. Under **Build and deployment**, choose **Deploy from a branch**.
6. Select the `main` branch and the `/ (root)` folder, then click **Save**.
7. GitHub will build the site and provide its public URL on the Pages settings screen.

For a project site, GitHub Pages may publish under a path such as:

```text
https://your-username.github.io/your-repository/
```

The templates use `relative_url`, so links and CSS continue to work when the site is published under a repository subpath. If needed, set the repository path in `_config.yml`:

```yaml
baseurl: "/your-repository"
url: "https://your-username.github.io"
```

For a user or organization site at `your-username.github.io`, keep `baseurl` empty.

## GitHub Pages notes

The included `Gemfile` uses standard Jekyll and `jekyll-seo-tag`. GitHub Pages can build many Jekyll sites automatically, but if your repository uses a custom GitHub Actions workflow, install the dependencies and run:

```bash
bundle exec jekyll build
```

The generated static site will be placed in `_site/`. Do not edit `_site/` directly; it is generated output.

## Customization

- Update the introduction in `index.md`.
- Change colors, typography, spacing, and responsive behavior in `assets/css/style.css`.
- Adjust the shared header and footer in `_layouts/default.html`.
- Adjust the song-page presentation in `_layouts/song.html`.
- Add more sections to `index.md` if you want playlists, listening notes, or a methodology section.
