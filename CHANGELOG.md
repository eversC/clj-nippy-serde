# Change Log
All notable changes to this project will be documented in this file. This change log follows the conventions of [keepachangelog.com](http://keepachangelog.com/).

## [0.1.2] - 2020-11-04
### Security
- Bump `com.taoensso/nippy` from `2.14.0` to `2.15.0` to fix
[CVE-2020-24164](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-24164)

## [Unreleased]
### Changed
- Add a new arity to `make-widget-async` to provide a different widget shape.

## [0.1.1] - 2018-04-14
### Changed
- Documentation on how to make the widgets.

### Removed
- `make-widget-sync` - we're all async, all the time.

### Fixed
- Fixed widget maker to keep working when daylight savings switches over.

## 0.1.0 - 2018-04-14
### Added
- Files from the new template.
- Widget maker public API - `make-widget-sync`.

[Unreleased]: https://github.com/your-name/clj-nippy-serde/compare/0.1.1...HEAD
[0.1.1]: https://github.com/your-name/clj-nippy-serde/compare/0.1.0...0.1.1
