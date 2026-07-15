# Bin Space - marketing website

Static marketing site for [Bin Space](https://www.bin-space.app), built with
[Quarkus Roq](https://iamroq.dev/) and deployed to GitHub Pages at
`www.bin-space.app`.

## Layout

- `src/main/resources/content/` - pages (`index.html`, `apps.html`)
- `src/main/resources/templates/layouts/` - Qute layouts (`default.html`)
- `src/main/resources/public/` - static assets served as-is (CSS, images, `CNAME`)

## Local dev

```shell
mvn quarkus:dev
```

Then open <http://localhost:8080>. Live reload applies content and CSS changes.

## Static build

```shell
QUARKUS_ROQ_GENERATOR_BATCH=true mvn package quarkus:run -DskipTests
```

The generated site lands in `target/roq/`.

## Deploy

Pushes to `main` trigger `.github/workflows/deploy.yml`, which uses the official
`quarkiverse/quarkus-roq` GitHub Action to build the site and publish it to
GitHub Pages.
