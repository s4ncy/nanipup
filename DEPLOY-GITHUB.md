# Publish Nani Pup on GitHub Pages

The repository is prepared for automatic deployment of **https://nanipup.eu** with GitHub Pages.

## 1. Create the repository

Create a new GitHub repository, for example `nanipup-eu`.

Upload **the contents of this folder into the repository root** (do not upload the parent folder as one nested directory).

The default branch should be `main`.

## 2. Enable GitHub Pages

In the repository open:

**Settings → Pages → Build and deployment → Source → GitHub Actions**

The included workflow `.github/workflows/deploy.yml` runs whenever a change is pushed to `main`.

## 3. Set the custom domain

In **Settings → Pages → Custom domain**, enter:

`nanipup.eu`

When DNS has propagated, enable **Enforce HTTPS**.

The Astro config is already set to `https://nanipup.eu` and `public/CNAME` is included.

## 4. DNS for nanipup.eu

At the domain/DNS provider, point the apex domain `@` to GitHub Pages using these A records:

- `185.199.108.153`
- `185.199.109.153`
- `185.199.110.153`
- `185.199.111.153`

Optional IPv6 AAAA records:

- `2606:50c0:8000::153`
- `2606:50c0:8001::153`
- `2606:50c0:8002::153`
- `2606:50c0:8003::153`

For `www`, add a CNAME pointing to `<YOUR-GITHUB-USERNAME>.github.io`.

Remove old conflicting `A`, `AAAA`, `ALIAS`, `ANAME` records for `@` and old `www` CNAME records before switching, unless they are required by another service.

## 5. Before selling products

The website itself can go live now. Current enquiry forms use the visitor's email app (`mailto:`), and the shop presents the Nani Goods catalogue but does **not** yet process card payments.

Before accepting online purchases, connect a checkout/payment provider and add the appropriate legal/privacy/terms content for that setup.

## Local development

```bash
npm install
npm run dev
```

Production build:

```bash
npm run build
```
