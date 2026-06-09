# Changelog

This file contains selected notable changes for ZANACMS. It is not intended to be a full commit log.

---

## [2.0.x] - 2026-06-xx (First public ZANACMS V2 release)

ZANACMS V2 is the first public release of the new ZANACMS code line. It combines the established PHP-page workflow with MD mode, Rich mode and a shared runtime, layout and language system

### Highlights

* Added two additional operating modes: MD mode for Markdown-based sites and Rich mode for editor-maintained page content, alongside the established PHP mode for developer-controlled PHP pages
* Added a shared layout system using `<family>/<design>` layout names, with included `html/water`, `html/just-the-docs[.dark]` and `wondercms/sky` layouts and support for additional external design families, including WordPress-based layouts from the earlier ZP line
* Added a clearer package structure with separate areas for configuration, admin tools and pages, alongside the established runtime, image and layout areas (`/__config`, `/admin`, `/pages`, `/zp`, `/img`, `/layout`)
* Added built-in multilingual site handling across PHP, MD and Rich mode, based on matured ideas from the earlier ZANACMS work
* Added central internal link and language handling for PHP, MD and Rich content, including `zlink()`, `zhref()` and page-language support
* Added optional URL rewrite support in the configuration and example `.htaccess` files
* Added Rich text editing with visual editing, HTML source editing, page-image selection, page management and navigation editing
* Added Markdown editing with toolbar support, ZMD links/images, variables and front matter support for PHP pages and layout images
* Added a media centre for browsing, uploading, inserting and deleting images
* Added device-cookie management for access to optional admin tools without introducing a public login system
* Added optional admin tools for system status, backup workflow, GitHub-based update workflow and one-step timeshift rollback, hidden by default
* Added an admin settings page for selecting the active design and editing a sidebar when the selected design supports one
* Added HTML cache support for supported layout generators to keep generated pages fast while preserving a small runtime
* Added documented public customisation interfaces for footer tokens, page variables, HTML layouts and local layout generators, alongside established configuration and CSS overrides
* Published under the ZANACMS Community License model for private, educational and non-commercial use, with commercial site licensing for productive commercial websites

---

## Project history

ZANACMS V2 continues an older design line, but its direct code base is ZP

* ZANACMS V1 was originally designed in 2005 and used commercially for over 15 years. Many ideas and concepts originate from it
* ZANAPRESS (ZP-WPTA) was developed in 2014 and published later as a small, very low-maintenance WordPress theme adapter
* ZANACMS V2 grew from the ZP code line: a simple, database-free and maintenance-friendly runtime with an optional admin layer, two additional content modes (MD and Richtext) and matured ideas from the earlier ZANACMS work
