# UFTB Cover Page Generator

A single-file web tool that creates ready-made **cover pages for assignments and lab reports** at the University of Frontier Technology, Bangladesh (UFTB). Fill in the details, pick a template, and download an A4 PDF, optionally merged with your main assignment PDF.

Everything runs in the browser. There is no backend, no account and no upload to any server.

## Features

- **5 templates:** UFTB Official, IEEE, Classic, Modern and Bold
- **Assignment and Lab Report** modes, with labels that switch automatically
- **Live A4 preview** that updates as you type
- **PDF merge:** add your assignment PDF and get one file with the cover first
- **Auto-fill:** name, ID, session, department and faculty are saved after the first login
- **Custom logo:** drop `logo.png` next to `index.html`, or pick an image once (it is saved in the browser)
- **Bengali interface** and a responsive layout for desktop and mobile

## Quick start

1. Download or clone the repository.
2. Open `index.html` in a modern browser.
3. Enter your details on the login screen (only needed once).
4. Fill in the cover page form, choose a template and press **কভার পেজ PDF ডাউনলোড**.

To merge with your assignment, drop its PDF into step 3 first. If the assignment is a Word file, export it to PDF before uploading.

### Logo

| Method | How |
| --- | --- |
| Auto-load | Place `logo.png` in the same folder as `index.html` and serve the folder over HTTP |
| Manual | Press **বাছুন** in the *Template & Logo* section and choose an image |

Browsers block `fetch` of local files when a page is opened directly from disk (`file://`). In that case use the manual option, or serve the folder:

```bash
python -m http.server 8000
# then open http://localhost:8000
```

## Deploy on GitHub Pages

1. Push the files to a repository.
2. Go to **Settings → Pages**.
3. Under *Build and deployment*, select **Deploy from a branch**, then `main` and `/ (root)`.
4. Your site will be available at `https://<username>.github.io/<repo>/`.

## Project structure

```
.
├── index.html   # the whole app (HTML, CSS and JavaScript)
├── logo.png     # optional university logo
└── README.md
```

## Built with

- Vanilla HTML, CSS and JavaScript
- [html2canvas](https://github.com/niklasvh/html2canvas) to render the cover as an image
- [pdf-lib](https://github.com/Hopding/pdf-lib) to build the PDF and merge pages
- Google Fonts: Hind Siliguri, Inter, Playfair Display, Tinos

The page loads these libraries and fonts from a CDN, so an internet connection is needed the first time.

## Privacy

Your details are stored only in your browser's `localStorage`. Uploaded PDFs are processed locally and never leave your device. Use **লগআউট** to clear the saved profile.

## Notes

- Encrypted or corrupted PDFs may fail to merge.
- The cover is exported as a high-resolution image inside the PDF, so its text is not selectable.

## Contributing

Issues and pull requests are welcome, especially for new templates or other departments' formats.

## License

Add a license of your choice (for example MIT) before publishing.
