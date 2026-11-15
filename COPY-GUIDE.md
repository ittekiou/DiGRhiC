# Copy This Commons 🌱

**From Solo Gardens to Multiplayer Gardens**

DiGRhiC is an experimental Digital Garden Commons built with DyXis and SLL/JP.

You can copy it, give it a new name, and connect it to other gardens.

No central registry. No framework lock-in.

## 1. Create Your Commons

1. Open the [DiGRhiC template](https://github.com/ittekiou/DiGRhiC/generate).
2. Choose a repository name.
3. Select **Public**.
4. Create your repository.

The default `main` branch is sufficient. You do not need to include all branches.

## 2. Edit `nest.json`

Update:

- `name` — your Commons name
- `url` — your published address, ending in `/`
- `about` — a short introduction
- `lang` — your preferred language
- `updated` — the date you last updated the sign
- `feeds` — your own RSS or Atom feeds
- `links` — optional links to other pages
- `nests` — the nests you want to reference

For a repository named `my-garden` owned by `yourname`, the usual GitHub Pages address is:

`https://yourname.github.io/my-garden/`

Your sign will be published at:

`https://yourname.github.io/my-garden/nest.json`

The `nests` field lists references, not memberships or confirmed relationships.

## 3. Edit `README.md`

Replace the DiGRhiC introduction with your own.

The Commons homepage displays this README above the map.

This works when your Commons is served from a `github.io` address. On a custom domain, the `about` text from your `nest.json` is shown instead.

You may keep, rewrite, or remove the original text.

## 4. Customize `index.html`

Update the Commons-specific settings:

- Page title and meta description
- The `HOME` fallback URL — used only when you open `index.html` directly from your computer. Usually no change is needed.
- Navigation links, if you want different destinations

The interface is already in English.

You do not need to translate or modify the map, crawling, or feed-handling code.

Icon paths are relative, so they work as they are. Replace the copied icons (`favicon.png`, `apple-touch-icon.png`) with your own when ready.

## 5. Initialize `feeds.json`

Recommended. The collector rewrites the whole file on its first run, so old data never stays for long. Initializing simply keeps another Commons' collection history from showing on your map until then.

Replace the file contents with:

```json
{
  "sll": "0.1",
  "commons": "https://yourname.github.io/my-garden/",
  "collected_at": null,
  "nests": {}
}
```

The collector will generate new data after it runs successfully.

## 6. Enable GitHub Pages

Open **Settings → Pages**.

Under **Build and deployment**, select:

- Source: `Deploy from a branch`
- Branch: `main`
- Folder: `/ (root)`

Save and wait for publication.

## 7. Enable Feed Collection

The repository includes `.github/workflows/collect.yml`.

The workflow already requests write access (`permissions: contents: write`), so there is usually nothing to change. If the commit step fails, check **Settings → Actions → General → Workflow permissions**.

Open **Actions → Collect feeds → Run workflow**.

Check the workflow result and the generated `feeds.json`.

The scheduled collector runs twice daily, using the times defined in the workflow.

## 8. Visit Your Commons

Open your GitHub Pages address.

Check that:

- Your Commons name and README appear
- Your `nest.json` loads
- The map starts from your Commons
- The intended nests appear
- The English interface displays correctly, including nest cards, feed timestamps, and map navigation
- Feed collection works

You can now share your Commons address.

Tip: when you upload files on GitHub, write a short commit message instead of the default "Add files via upload". If your sign lists your commit feed, that message becomes the news line on the map.

---

## What Usually Needs No Changes?

- `scripts/collect.py`
- The map's crawling and drawing logic
- `.github/workflows/collect.yml`, including its schedule (unless you want different collection times) and its write permission

The collector normally determines its starting address from the GitHub repository environment.

## One More Possibility

You can enable **Settings → General → Template repository** on your own repository.

Then other people can copy your Commons, too.

---

**Your garden. Your address. Your connections.**

*Everything begins with solo play.*

🐜🌱
