# Changelog

This file contains selected notable changes for ZANACMS. It is not intended to be a full commit log.

---

## [2.0.6] - 2026-06-20 (First public ZANACMS V2 release)

ZANACMS V2 is the first public release of the new ZANACMS code line. It combines the established PHP-page workflow with MD mode, Rich mode and a shared runtime, layout and language system

### Highlights

- Three operating modes: PHP mode for developer-controlled pages, MD mode for Markdown-based sites, Rich mode for editor-maintained page content
- Database-free operation, plain-file structure, no build pipeline
- Built-in multilingual handling across all three modes, including central link and language functions (zlink(), zhref()) and page-language support
- Shared layout system with <family>/<design> naming; included layouts: html/water, html/just-the-docs[.dark], wondercms/sky; support for additional external design families including WordPress-based layouts
- Generated sitemap.xml with multilingual hreflang alternates and lastmod dates
- Optional URL rewrite support

- Rich mode: visual editing, easy link and image support, HTML source editing
- MD mode: toolbar support, easy link and image support, variables and front matter, including support for PHP pages
- Media centre for browsing, uploading, inserting and deleting images

- Admin exposure levels from easy mode to full option visibility
- Optional service access for agencies and maintainers, including preview of lower admin exposure levels
- Device-cookie access management for admin tools without a public login system
- Optional admin tools for system status, backup, GitHub-based update workflow and one-step timeshift rollback, hidden by default
- Documented public customisation interfaces: footer tokens, page variables, HTML layouts, local layout generators, configuration and CSS overrides

- Clearer package structure: /__config, /admin, /pages, /zp, /img, /layout
- ZANACMS Community License: free for private, educational and non-commercial use; commercial site licence for commercial production sites

---

## Project history

ZANACMS V2 continues an older design line, but its direct code base is ZP

* ZANACMS V1 was originally designed in 2005 and used commercially for over 15 years. Many ideas and concepts originate from it
* ZANAPRESS (ZP-WPTA) was developed in 2014 and published later as a small, very low-maintenance WordPress theme adapter
* ZANACMS V2 grew from the ZP code line: a simple, database-free and maintenance-friendly runtime with an optional admin layer, two additional content modes (MD and Richtext) and matured ideas from the earlier ZANACMS work
