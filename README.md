# Preview Attachment

A Frappe app that lets users **preview file attachments** directly inside the desk, without having to download them first.

> Compatible with **Frappe / ERPNext v15** (`>=15.0.0,<16.0.0`).

## Features

- Preview attached files from the document sidebar / attachments section
- No need to download a file just to look at it
- Works as a standalone app on top of any Frappe site

> Edit this list to match exactly what the app supports (file types, where the preview button appears, etc.).

## Installation

### Self-hosted bench

```bash
cd $PATH_TO_YOUR_BENCH
bench get-app https://github.com/altamash125/Preview-Attachment.git --branch main
bench --site <your-site-name> install-app preview_attachment
bench --site <your-site-name> migrate
bench build --app preview_attachment
bench restart
```

### Frappe Cloud

1. Go to **Apps → Add App → Add from GitHub**.
2. Select the repository `altamash125/Preview-Attachment` and the `main` branch.
3. Add the app to your bench group, then deploy.

The app declares its Frappe version in `pyproject.toml`:

```toml
[tool.bench.frappe-dependencies]
frappe = ">=15.0.0,<16.0.0"
```

If your bench runs a different Frappe version, update this range before deploying.

## Usage

1. Open any document that has file attachments.
2. Use the preview option on an attachment to view it in place.

## Development

```bash
cd apps/preview_attachment
git checkout main
bench --site <your-site-name> set-config developer_mode 1
bench start
```

After changing JS or CSS, run `bench build --app preview_attachment` (or keep `bench start` running for live rebuilds).

## Credits

Originally created by Hardik Zinzuvadiya. Maintained by [altamash125](https://github.com/altamash125).

## License

See the license file in this repository for details.
