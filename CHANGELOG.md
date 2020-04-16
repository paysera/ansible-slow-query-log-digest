# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## 1.0.1 - 2020-04-16

### Fixed
- Due to line split in `pt-query-digest` command on `--review` and `--history` flags, command created new tables instead of writing to existing ones. Line split was removed 

### Changed
- Extract global variables to local variables to reduce line length

## 1.0.0 - 2020-04-15

### Added
- Initial role commit
