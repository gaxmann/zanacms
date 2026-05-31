# Changelog

This file contains selected notable changes for ZANACMS. It is not intended to be a full commit log.

---

## [2.4.71] - 2026-05-31 (Github udpate check removed)

### Changed
- Github automatic update check removed, introduced 

## [2.4.68] - 2026-05-30 (__config optimisation)

### Changed
- All `__*` files are moved to the /__config. Breaks compatibility, but V2 was never published #2.4.62
- Cache now also sets the available language of a page
- Docs updated. Example files optimised

## [2.4.54] - 2026-05-28 (Timeshift)

### Added
- Update script now creates a timeshift that you can revert to (only 1 step) #2.4.54
- Folder `admin/lang` now also accepts new languages (from ?lg= or __conf/stdlang) #2.5.57

## [2.4.45] - 2026-05-28 (MD editor)

### Added
- MD editor now has a toolbar #2.4.35
- Fixes for double urlescapes, MD cache simpler with zlink(). Code cleanup
- HTML sanitasation reduced to allow more options #2.4.42
- Update to stable option was missing #2.4.45

## [2.4.21] - 2026-05-28 (Admin email)

### Added
- Added an update checking system (Github) to inform admin about necessary updates (and a update policy file) - email delivery must be activated in config. If you run a critical version, you can get an email and the admin status table will inform you about it #2.4.18
- Added `_` functionality to the MD editor

## [2.4.5] - 2026-05-28 (Admin status table)

### Added
- Added a system status table to the welcome admin page (which is open therefore the table is only shown to devices with auth)

## [2.4.1] - 2026-05-27

### Changed
- Added a new PHP link-language scheme: `$GLOBALS['zdata']['lg']` can be set manually for page language handling when `zautolg()` is not used #2.3.123
- Added the simpler PHP helper `zhref('pageid', 'Link text')` for internal links
- Moved admin language strings to `/admin/lang/*` #2.3.119
- Selected a Community License for ZANACMS 2

### Fixed
- Fixed an Error 502 issue caused by endless recursion in Rich mode language handling

## [2.3.109] - 2026-05-27

### Added
- Added backup/update tooling to back up a website or update system files from GitHub
- Added an `isdev.txt` check in `/zp` for development-only behaviour #2.3.111

## [2.3.103] - 2026-05-27

### Added
- Added a delete button for images in the media centre
- Added ZMD image syntax: `![alignright|Alt text for image](img/demo.jpg)`
- ZMD image output now inserts a small image and automatically links to a larger image if a matching file exists in `/img/big` or if the image in `/img/` is already larger than the configured small output size
- Normal Markdown image behaviour is kept for `![](https://...)`, `![](http://...)` and `![](/directory/image.png)`
- Links to larger images are now also added when the image in `/img/` is already large, even if no separate larger file exists in `/img/big`

## [2.3.87] - 2026-05-26

### Changed
- Optimised runtime performance in several places
- Added an updater script at `/admin/_upd.php` to download ZANACMS from GitHub and install it

## [2.3.85] - 2026-05-26

### Changed
- Changed the HTML variable placeholder to `~~ZBASEURL~~` because it is easier to use in links and avoids URL encoding issues
- Tested the GitHub downloader

## [2.3.63] - 2026-05-25

### Changed
- Removed regular-expression-based layout URL handling
- Introduced `{%%ZP_BASEURL%%}` for layouts to support URL rewrite handling
- Updated layouts accordingly

## [2.3.57] - 2026-05-25

### Added
- Added the new `zlink()` function for internal links in PHP and for cached ZMD link syntax such as `[@contact]` and `[[@contact]]`
- Added optional URL rewrite support in the configuration and `.htaccess` example files

### Changed
- Cleaned up code #2.3.60
- Updated PHP navigation examples to use the new forma #2.3.62

## [2.3.46] - 2026-05-25

### Changed
- Moved all admin files to `/admin`
- `/admin` can now be removed in PHP mode, or in MD mode when Markdown files are edited directly by FTP, because all runtime files remain in `/zp`
- Moved `layout/html/zpgen.php` to `/zp`, because it is required by the ZANACMS runtime

## [2.3.41] - 2026-05-24

### Added
- Added an admin page overview to show, edit and delete languages and pages
- In Rich mode and MD mode, `noindex` and `mode` are now page-wide values and apply to all language versions of a page

## [2.3.37] - 2026-05-24

### Changed
- Renamed the project to ZANACMS
- Added a centre-alignment button to the Rich editor

## [2.3.36] - 2026-05-24

### Changed
- Renamed `titel` to `sitetitel` and `subtitel` to `sitesub` to reduce ambiguity

## [2.3.33] - 2026-05-24

### Added
- Added `htmllast` to HVARS

## [2.3.27] - 2026-05-24

### Added
- Added `zgen_hvars()` as the central function for HTML/cache variables. Generators now send their output through `zgen_hvars()`
- Extended `zhtmlcachrepl()` to use the same central function and an equivalent ignore list
- Added a code button to the Rich editor

### Changed
- Renamed the HTML variable `bodyend` to `bodylast` system-wide, including `{%%ZP_BODYLAST%%}` and `$GLOBALS['zconf']['bodylast']`
- Moved generator `<title>` and robots meta handling into `zgen_hvars('head', ...)`

## [2.3.23] - 2026-05-23

### Added
- Added a `<>` button to the Rich editor to toggle between the visual editor and an editable HTML source textarea

## [2.3.11] - 2026-05-22

### Added
- Added a page image selector to the editors. The selected `pageimg` can be inserted at a predefined position in a design.
- If no explicit position is available, the page image is inserted near the start of the body, inside the first paragraph #2.3.8
- Added text sanitation for content copied from office documents into the Rich editor

## [2.3.1] - 2026-05-22

### Added
- Added Rich mode with the Squire HTML rich text editor for editing web pages
- Added a new navigation editor for Rich mode. It edits navigation entries in `/pages/__navi.data.php`, similar to the MD mode navigation file `/pages/__NAVIGATION.txt`

## [2.2.29] - 2026-05-21

### Added
- Added MD front matter support for `mode: php`. This loads `./pages/<pageid>.php` instead of Markdown page data, allowing complex PHP pages inside MD mode.
- Added MD front matter support for `layoutimg`.

## [2.2.21] - 2026-05-20

### Added
- Added variables for MD mode, defined in `/pages/zvars.php`.
- The MD editor now has a select field for inserting variables into a page.
- ZANACMS replaces variable names with variable content at runtime without caching via `zvars.php`. This is useful when an MD user needs PHP-generated output prepared by a programmer.

## [2.2.15] - 2026-05-19

### Changed
- Added `/layout/html` as a layout family for custom designs based on a `design.html` template with ZP variables.
- Custom assets can be used directly by the design.
- If a custom generator is required, it should be created as a new layout family under `/layout/<family>/_generator/zpgen.php`.
- Renamed the `wonder` layout family to `wondercms`.

## [2.2.9] - 2026-05-19

### Added
- Added direct `zpdesign.html` generation for older WordPress 2015 themes to improve compatibility with newer PHP versions.
- The themes `editor`, `generatepress`, `graphy`, `independent-publisher-2`, `minnow`, `noto-simple`, `seedlet`, `sosimple` and `syntax` are now generated directly from `zpdesign.html` without using HTML cache or PHP theme generation.

## [2.2.1] - 2026-05-18

### Added
- Added an optional layout whitelist, allowing website designs to be changed with `?lay=<design>` when the requested value is allowed.
- Automatically sets `noindex` when the layout selector is used.
- Clarified the generator directory layout introduced in the 2.2 series.

## [2.1.117] - 2026-05-17

### Added
- Added `zconf['layoutimg']` to place a layout image into designs. It can be overridden by local page data. #2.1.116
- Added the `paradigm-shift/paradigm-shift` design with a new generator.
- The Paradigm Shift generator now renders nested navigation items and the language selector as collapsible dropdowns.

## [2.1.111] - 2026-05-17

### Changed
- Moved the ZP generator directory to `/layout/_zpgen/<family>`.
- A local generator under `/layout/<family>/_generator/zpgen.php` now takes precedence, making it possible to support new layouts while keeping backwards compatibility.
- Introduced `FOOT0` and `FOOT1` variables for more complex HTML designs.
- Added a central HTML cleaning function for generators.
- Tested caching for small generators such as water and pico; no clear performance gain was found.
- The device manager can now clear all HTML cache files. #2.1.111

## [2.1.101] - 2026-05-17

### Changed
- Moved all generators into the layout directory, so people do not have to modify the `/zp` directory for layout work.
- Generator variants are now selected with the `family.variant/design` syntax. #2.1.103

## [2.1.100] - 2026-05-17

### Added
- Improved the WordPress 2015 generator to work with more older themes.
- Added jQuery scripts in a script folder to support older themes.

## [2.1.94] - 2026-05-17

### Changed
- Optimised footer generation and cleaned up code.
- Updated manuals.
- Added separate mobile navigation to the WonderCMS/Sky and water designs.
- Corrected the loading order for custom CSS.

### Fixed
- Fixed several bugs.
- Fixed a horizontal scrollbar issue in the Sky mobile navigation. #2.1.98

## [2.1.70] - 2026-05-16

### Added
- Added `zpsuper.css` for general image rules.
- Removed these image rules from individual `zp.css` files.
- Renamed `super.css` to `supercustom.css`. #2.1.70

## [2.1.68] - 2026-05-16

### Added
- Added HTML cache support to `wordpress.2015`, `wordpress.2026` and Editorial after the initial caching implementation for WonderCMS/Sky.
- The cache is renewed when the generator file or `zp.css` is newer than `zpcache.html`. #2.1.66

### Changed
- Changed the memory-cache prefix from `BUFF_` to `MCACH_`. #2.1.63

## [2.1.61] - 2026-05-15

### Added
- Integrated the WonderCMS/Sky design with a separate WonderCMS generator.

## [2.1.60] - 2026-05-15

### Added
- The device manager is now also accessible through an existing editing cookie. In this mode, no new devices can be added; it only lists activated devices and allows deleting all activations. #2.1.40
- Restored status output. #2.1.53
- Improved image upload logic.
- Cleaned up code.

### Fixed
- Already activated devices can now extend their access period

## [2.1.36] - 2026-05-14

### Added
- Added an admin link list at `_admin.php`

### Changed
- Renamed the editor and media centre files to `_e.php` and `_m.php`
- Moved device-manager enabling to `/__EDITACCESS_ENABLE.php` from the previous `__zdocook_enable.txt`

## [2.1.24] - 2026-05-13

### Added
- Added support for multiple editing devices
- The helper page now lists stored user agents, expiry dates and rounded remaining days, and removes expired access entries
- The helper is locked by a text file. Writing `5,1` into that file opens it for up to five minutes and allows one new device cookie
- The helper resets the file to `0,0` after the last allowed new device cookie or after expiry

## [2.1.19] - 2026-05-12

### Added
- Added a media gallery for viewing images in `/img` and copying HTML or PHP code
- Like the MD editor, the gallery is inactive by default and can be enabled through the editing-cookie setup

## [2.1.10] - 2026-05-10

### Added
- Added a Markdown editor to edit and create MD pages

## [2.0.0] - 2026-05-07

### Added
- Added `pico.css` and `water.css`, including two new generators, to support CSS design themes outside the WordPress theme flow
- Added MD mode to create web pages from Markdown files
- Added new link and navigation logic
- ZANACMS can now run in PHP mode or MD mode

---

## [1.0.0 - 1.0.8] - 2014..2026

### Added
- Developed ZANAPRESS as a WordPress theme adapter to reduce the maintenance workload associated with WordPress websites, especially when maintaining several of them
