# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

This project is a fork of [Yetangitu/bs](https://github.com/Yetangitu/bs),
via [PinkFreud/bs](https://github.com/PinkFreud/bs).

## [Unreleased]

## [0.1.0] - MacLeod92/bs

### Added
- New `section update` subcommand to replace a single section by heading in a page's markdown.
- `-w` flag for `section read` and `section update` to include the heading line in output/input. Without `-w` (the default), the heading is excluded from read output and left unchanged by update.

### Fixed
- `section update` was failing with "required parameter(s) missing: id" due to `OPTIND` not being reset before `crud()` was called. `crud()` now resets `OPTIND=1` on entry.
- `section read` now exits with an error if the section is not found, rather than silently returning nothing.

## [0.0.4] - MacLeod92/bs

### Fixed
- Malformed JSON in `pages`/`chapters`/`books` create/update when `-m`/`-h`
  is given without `-n`/`-d`/`-t`. The comma between `$data` and
  `$content_type` is now only included when `$data` is non-empty.

## [0.0.3] - PinkFreud/bs

### Fixed
- `bs` now works if config only specifies named tokens/urls, lacking
  top-level `token=`/`url=` entries.
- Query-string construction for `search`, `list` (books, chapters, pages,
  attachments, shelves, users) and `recycle-bin list`. Query parameters
  were being passed into the `id` argument of `get()` rather than appended
  to the URL.
- `get()` now accepts an `opts` argument and appends it to the URL as `?...`.

## [0.0.2] - Yetangitu/bs

### Added
- `-U USERNAME` / `-H HOSTNAME` parameters for named tokens/urls in `bs.conf`.
- README documentation for named host/user configuration and `BS_OPTIONS`.
- Reduced curl verbosity.

## [0.0.1] - Yetangitu/bs

### Added
- Initial release.

[0.1.0]: https://github.com/MacLeod92/bs/compare/v0.0.4...v0.1.0
[0.0.4]: https://github.com/MacLeod92/bs/compare/v0.0.3...v0.0.4
[0.0.3]: https://github.com/MacLeod92/bs/compare/v0.0.2...v0.0.3
[0.0.2]: https://github.com/MacLeod92/bs/compare/v0.0.1...v0.0.2
[0.0.1]: https://github.com/MacLeod92/bs/releases/tag/v0.0.1
