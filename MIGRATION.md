# WordPress migration

Imported on 25 October 2026 from `charles:/var/www/html/blog_old`, using a read-only database connection parsed on the server from `wp-config.php`. No database credentials were copied into this repository. The source website was not modified.

- 138 published posts (2016–2024) in `_posts/`.
- 5 published pages in `_pages/wordpress/`.
- 1,214 media files, including image variants, a PDF, and a video, in `blog/wp-content/uploads/`.
- 16 approved comments retained as static comments under their original posts.
- Original titles, publication and modification dates (UTC+07:00), author names, categories, tags, and featured images retained.
- Historical `/blog/<slug>/` paths retained through explicit permalinks. Internal links to the old blog domains now resolve locally.
- Blog archive at `/`; category and tag archives at `/categories/` and `/tags/`. `/blog/` redirects to the root, and `/posts/` remains available. The personal homepage and Experiences page have been removed.

Post bodies use HTML with YAML front matter to retain WordPress formatting, code examples, captions, and embedded content. Existing embedded services may depend on their providers. A broken Facebook link from an old saved-page export was repaired using the Facebook URL already present in that post.

The publishing domain is `blog.srakrn.me`, also used for canonical URLs. Redirecting old domains, WordPress query-string URLs such as `?p=123`, and attachment pages requires hosting configuration; the source WordPress server remains unchanged. GitHub Actions builds and deploys pushes to `master` using `.github/workflows/pages.yml`.

Drafts and the complete source content export remain in the sibling migration workspace under `private-source/`, outside this repository. Plugin settings, caches, executable PHP files, and unpublished content were excluded from the public site.

The migration was checked with a Jekyll build using Ruby 3.3.6 and the existing Gemfile. All 143 published content routes, approved comments, media checksums, archive pages, and local links were verified. `/` lists posts by year without pagination.

To build locally with Ruby 3.3.6 selected:

```sh
bundle install
bundle exec jekyll build
bundle exec jekyll serve
```
