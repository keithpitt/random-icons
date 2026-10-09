# Random Icons

A personal collection of SVG icons missing from other packs.

## Adding icons

1. Put each SVG directly in `icons/`, using a descriptive lowercase, hyphenated
   filename, such as `rotten-tomatoes-fresh.svg`.
2. Keep a `viewBox` on the SVG and preserve its original colors. Use self-contained
   SVGs without scripts, external resources, or embedded raster images.
3. Record the source URL, author, license or usage terms, and any modifications in
   `ATTRIBUTION.md`. Include any required license files in `licenses/`.
4. Commit and push to `main`.

The pack starts empty. No Rotten Tomatoes or other third-party assets are included yet.

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
The empty pack will not appear in the icon browser until an SVG is added.

For example, after adding `icons/rotten-tomatoes-fresh.svg`:

```erb
<%= unmagic_icon "random-icons/rotten-tomatoes-fresh", class: "size-6" %>
```

## Asset terms

This collection has no blanket license for its icons. Each asset retains its own
copyright, license, and trademark terms, recorded in `ATTRIBUTION.md` and any
accompanying files in `licenses/`.
