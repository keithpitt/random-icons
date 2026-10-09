# Random Icons

A personal collection of SVG icons.

## Adding icons

1. Put each SVG directly in `icons/`, using a descriptive lowercase, hyphenated
   filename, such as `rotten-tomatoes-fresh.svg`.
2. Keep a `viewBox` on the SVG and preserve its original colors. Use self-contained
   SVGs without scripts, external resources, or embedded raster images.
3. Record the source URL, author, license or usage terms, and any modifications in
   `ATTRIBUTION.md`. Include any required license files in `licenses/`.
4. Commit and push to `main`.

## Available icons

- <img src="icons/rotten-tomatoes-verified-hot-small.svg" alt="" height="32"> `rotten-tomatoes-verified-hot-small`
- <img src="icons/rotten-tomatoes-verified-hot.svg" alt="" height="32"> `rotten-tomatoes-verified-hot`
- <img src="icons/rotten-tomatoes-popcorn-empty.svg" alt="" height="32"> `rotten-tomatoes-popcorn-empty`
- <img src="icons/rotten-tomatoes-popcorn-stale.svg" alt="" height="32"> `rotten-tomatoes-popcorn-stale`
- <img src="icons/rotten-tomatoes-popcorn-hot.svg" alt="" height="32"> `rotten-tomatoes-popcorn-hot`
- <img src="icons/rotten-tomatoes-certified-fresh-small.svg" alt="" height="32"> `rotten-tomatoes-certified-fresh-small`
- <img src="icons/rotten-tomatoes-certified-fresh.svg" alt="" height="32"> `rotten-tomatoes-certified-fresh`
- <img src="icons/rotten-tomatoes-tomatometer-empty.svg" alt="" height="32"> `rotten-tomatoes-tomatometer-empty`
- <img src="icons/rotten-tomatoes-rotten.svg" alt="" height="32"> `rotten-tomatoes-rotten`
- <img src="icons/rotten-tomatoes-fresh.svg" alt="" height="32"> `rotten-tomatoes-fresh`
- <img src="icons/imdb.svg" alt="" height="32"> `imdb`
- <img src="icons/imdb-monochrome.svg" alt="" height="32"> `imdb-monochrome`
- <img src="icons/rotten-tomatoes.svg" alt="" height="32"> `rotten-tomatoes`

`imdb-monochrome` uses `currentColor`; all other icons retain their source colors.
The `-small` certification variants omit the badge text for small displays.
Empty-score icons are separate from negative ratings.

## Using with unmagic-icon

Add the pack to your Rails initializer:

```ruby
Unmagic::Icon.configure do |config|
  config.libraries = [:"random-icons"]
end
```

Install it:

```sh
bin/rails 'unmagic:icons:download[random-icons]'
```

After adding or updating icons, refresh the installed copy:

```sh
bin/rails 'unmagic:icons:download[random-icons,force]'
```

The downloader follows `main`. Existing installations are skipped unless forced.
A forced refresh overwrites matching files but does not remove deleted icons.

For example:

```erb
<%= unmagic_icon "random-icons/rotten-tomatoes-fresh", class: "size-6" %>
<%= unmagic_icon "random-icons/rotten-tomatoes-popcorn-hot", class: "size-6" %>
<%= unmagic_icon "random-icons/imdb", class: "size-6" %>
<%= unmagic_icon "random-icons/imdb-monochrome", class: "size-6 text-yellow-500" %>
```

## Asset terms

This collection has no blanket license for its icons. Each asset retains its own
copyright, license, and trademark terms, recorded in `ATTRIBUTION.md` and any
accompanying files in `licenses/`.
