# ZANACMS – Website Theme Engine

**For smaller websites — multilingual, design-flexible, database-free**

ZANACMS is not designed to compete with large CMS platforms, headless systems or modern JavaScript frameworks. It is built for a different problem: small and medium-sized websites that should remain easy to maintain, easy to move and easy to keep running for many years.

Most modern web stacks optimise for large applications and rapid feature development. ZANACMS instead focuses on long-term stability and straightforward deployment on ordinary PHP hosting — no database, no build pipeline, no    continuous framework maintenance.

_In production use since 2014._

---

## Why ZANACMS 2?

ZANACMS is built for websites that behave like static sites while still being generated dynamically. If your project needs complex web applications, user accounts or large-scale content management, other platforms will serve you better. If it needs a stable, low-maintenance website that keeps working for years — ZANACMS is designed for exactly that.

* **Fast on shared hosting** — excellent page generation times
* **No database** — plain files, simple backups and easy moves
* **No public login system by default** — small attack surface
* **Service login configurable** — for agencies and web administrators
* **Multilingual without plugins** — multiple languages are built in
* **Design-flexible** — included layouts and optional external designs
* **Three working modes** — PHP pages, Markdown files or Rich text editing
* **Small footprint** – core ZIP (1 design, FTP-managed): ca. **40 KiB**; full package ZIP (5 generators, 3 designs, two editors, 7-language admin, jQuery, etc.): ca. **400 KiB**

⚡ _In a comparison with a standard WordPress site containing similar content, ZANACMS was over **150× faster** and used over **15× less RAM** (0.5–2 ms vs. 150–400 ms; 1 MiB vs. 6–32 MiB; both on shared hosting)._

---

## Intended use

ZANACMS is mainly designed for small, long-lasting websites where structure, layout and functionality are set up once and page content can remain stable or be maintained separately.

A typical setup is a developer-built website where the owner edits normal page content through the Rich text editor, while layout, navigation and shared behaviour stay centrally configurable. ZANACMS can also be used entirely by a PHP developer in PHP mode, especially for stable sites that should keep running for many years with very little ongoing maintenance.

---

## Three modes

ZANACMS can run in **PHP mode**, **MD mode** or **Rich mode**. All three modes use the same ZP system files, language configuration, layout system and internal link logic.

| Mode | Use case |
| --- | --- |
| **PHP mode** | Pages prepare their own page data directly in PHP. Use this when you know PHP and want full control. |
| **MD mode** | Pages are written as Markdown files, edited directly or through the built-in Markdown editor. |
| **Rich mode** | Page content is maintained through the built-in rich text editor. |

---

## Start a site

Upload ZANACMS to a PHP-enabled web server, choose `php`, `md` or `rich` mode, copy the matching example configuration from `/__config/conf.example-*.php` to `/__config/conf.php`, copy the matching example `index.php`, and add your content.

For MD mode and Rich mode, copy the matching example page files from `/pages/example/md/` or `/pages/example/rich/` into `/pages/`.

The `/admin/` directory contains the optional admin tools. Rich mode needs it for the editor workflow; MD mode and PHP mode only need it for media gallery or optional editor.

URL rewrite is prepared but disabled by default. The full documentation is maintained in the separate [`zanacms-docs`](https://gaxmann.github.io/zanacms-docs/) documentation source.

_Actively tested with PHP 7.4 and 8.4. GD and json are only required for image uploads; iconv improves filename transliteration during uploads._

---

## Layouts

Layouts are selected as `<family>/<design>` and are stored in `/layout/<family>/<design>/`.

Included layouts:

* `html/water` — water.css
* `html/just-the-docs` — just-the-docs jekyll theme
* `wondercms/sky` — WonderCMS Sky theme

Additional designs can be placed under a matching layout family, for example WordPress themes, Editorial, Paradigm Shift or other external designs. Optional design files are **not** included in the ZANACMS package. 12 tested snapshots are kept in a separate repository:

```text
https://github.com/gaxmann/zp-cms-designs
```

The optional external designs are not part of the ZANACMS source code, are not covered by the ZANACMS Community License, and remain under their original upstream licences. Details are documented in [`THIRD-PARTY-NOTICES.md`](layout/THIRD-PARTY-NOTICES.md).

---

## 🌐 Demo

Live demos are available here:

* [ZANACMS demo with Water.css layout](https://axmann.eu/sunclock.php?lg=en&lay=html%2Fwater)
* [Just-the-docs layout](https://axmann.eu/sunclock.php?lg=en&lay=html%2Fjust-the-docs)
* [WonderCMS/Sky layout](https://axmann.eu/sunclock.php?lg=en&lay=wondercms%2Fsky)
* [Z-Airy](https://axmann.eu/sunclock.php?lg=en&lay=html%2Fz-airy)
* [Editorial layout](https://axmann.eu/sunclock.php?lg=en&lay=editorial)
* [Paradigm Shift layout](https://axmann.eu/sunclock.php?lg=en&lay=paradigm-shift)
* [WordPress/Graphy layout](https://axmann.eu/sunclock.php?lg=en&lay=wordpress%2Fgraphy)
* [WordPress/Syntax layout](https://axmann.eu/sunclock.php?lg=en&lay=wordpress%2Fsyntax)

---

## Optional editor and media gallery

Editor and media-gallery access is disabled by default and managed through the device manager and editing cookies.

When enabled, Rich mode and MD mode can show a small `[e]` footer link to the editor. PHP mode can show a small `[i]` footer link to the media gallery, which can upload images and copy the matching image code.

Rich mode uses the editor for normal page content. MD mode can use the Markdown editor or direct file editing, for example by FTP. PHP mode does not need the editor for normal runtime.

---

## Contributions and layout improvements

Help with layout improvements and additional design support is welcome: CSS adjustments, additional third-party themes, new layout families and improvements to existing layout generators.

If you notice rendering problems, missing CSS rules or layout inconsistencies, feel free to open an issue or suggest an improvement.

---

## More information

* [ZANACMS documentation](https://gaxmann.github.io/zanacms-docs/) — help pages and full guide
* [`zanacms-docs`](https://github.com/gaxmann/zanacms-docs) — documentation source repository

---

## Licence / Status

ZANACMS is source-available software. It is not OSI-certified open source. **Private, educational and non-commercial use is free of charge.** Commercial use requires a commercial site licence, valid for one productive website and all releases within the same major version. See [`LICENSE`](LICENSE) and [`LICENSE-FAQ.md`](https://gaxmann.github.io/zanacms-docs/guide/license-faq/).
