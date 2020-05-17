# Changelog

## 1.5.1 - 2020-05-16

### Changed
- Improved saving of new Redirects if matching 404 exists ([#26])
- Improved display of Base URL on Redirect edit page
- Updated `barrelstrength/sprout-base-redirects` requirement v1.5.1

[#26]: https://github.com/barrelstrength/craft-sprout-redirects/issues/26

## 1.5.0 - 2020-04-28

### Changed
- Updated `barrelstrength/sprout-base` requirement v6.0.0

### Fixed
- Fixed migration issue when multiple Sprout plugins are installed

## 1.4.0 - 2020-04-27

### Added
- Added example config file `src/config.php`
- Added `barrelstrength\sproutbase\base\SproutDependencyTrait`
- Added `barrelstrength\sproutbase\base\SproutDependencyInterface`
- Added `barrelstrength\sproutbase\records\Settings`
- Added `barrelstrength\sproutbase\migrations\Install::safeDown()`
- Added support for config overrides in base settings models

### Changed
- Improved uninstall migration
- Updated `barrelstrength/sprout-base` requirement v5.2.0
- Updated `barrelstrength/sprout-base-redirects` requirement v1.4.0

### Removed
- Removed `barrelstrength\sproutbaseredirects\services\getPluginSettings()`
- Removed `barrelstrength\sproutbase\services\Settings::getPluginSettings()`
- Removed `barrelstrength\sproutbase\base\BaseSproutTrait`

## 1.3.3 - 2020-04-09

### Changed
- Updated `barrelstrength/sprout-base` to v5.1.3

### Fixed
- Fixed welcome page display issue

## 1.3.2 - 2020-03-08

### Added
- Added Enable Redirects setting to turn Redirect behavior on or off ([#20][#20-sproutredirects])

### Changed
- Updated `barrelstrength/sprout-base-redirects` to v1.3.2

### Fixed
- Fixed bug where secondary sites redirected back to the main site ([#24][#24-sproutbaseredirects])
- Fixed 404 Redirect priority when matching a redirect

[#24-sproutbaseredirects]: https://github.com/barrelstrength/craft-sprout-redirects/issues/24
[#20-sproutredirects]: https://github.com/barrelstrength/craft-sprout-redirects/issues/20

## 1.3.1 - 2020-02-07

### Added
- Updated `barrelstrength/sprout-base-redirects` to v1.3.1

## 1.3.0 - 2020-02-05

### Added
- Added `sproutbaseredirects/elements/Redirect::pluralDisplayName()`

### Updated
- Updated Redirect Element Index to support Craft 3.4
- Updated models to use `defineRules()` method
- Refactored asset management
- Updated `barrelstrength/sprout-base-redirects` to v1.3.0

## 1.2.4.1 - 2019-12-18

### Fixed
- Fixed broken link to settings on Plugins page

## 1.2.3.2 - 2019-12-10

### Changed
- Added method heading in Redirect sources sidebar 
- Updated barrelstrength/sprout-base-redirects requirement to v1.2.2

### Fixed
- Added missing columns to Install migration [#19]
- Fixed `dateLastUsed` column type
- Fixed database prefix errors [#1][1pull-sprout-base-redirects]

[#19]: https://github.com/barrelstrength/craft-sprout-redirects/issues/19
[1pull-sprout-base-redirects]: https://github.com/barrelstrength/craft-sprout-base-redirects/pull/1

## 1.2.2 - 2019-11-22

### Fixed
- Fixed bug where database migrations did not get triggered

## 1.2.1 - 2019-11-22

### Changed
- Updated barrelstrength/sprout-base-redirects requirement to v1.2.1

### Fixed
- Fixed support for database prefixes when finding URLs [#18][18-sprout-base-redirects]

[18-sprout-base-redirects]: https://github.com/barrelstrength/craft-sprout-redirects/issues/18

## 1.2.0 - 2019-11-19

> {tip} This release is a recommended upgrade. Updates include improvements to the redirect workflow including how query strings are handled, managing excluded URLs from tracking, performance improvements around finding and cleaning up 404 Redirects, and several bug fixes include a potential security issue.

### Added
- Added 'Redirect Match Strategy' setting to control how query strings are handled when matching incoming redirects ([#6], [#16])
- Added 'Query String Strategy' setting to control if a query string is appended or removed when redirecting to a new URL ([#6], [#16])
- Added 'Clean Up Probability' setting to control the frequency that 404 Redirect cleanup tasks are triggered
- Added Last Remote IP Address, Last Referrer, Last User Agent, and Date Last Used fields to Redirect Elements ([#7], [#10])
- Added 'Track Remote IP' setting to enable/disable whether IP Address is stored in the database
- Added 'Excluded URL Patterns' setting to filter URL patterns you don't wish to log as 404 Redirects
- Added 'Add to Excluded URLs' Element Action to quickly add one or more 404 Redirects to the 'Excluded URL Patterns' setting

### Changed
- Improved performance when finding a match for an incoming URL
- Added the Redirect 'Data Last Used' field as default table attribute on the Element Index page ([#7])
- Updated Redirect 'RegEx' field to be named 'Match Strategy' with the strategies `Exact Match` and `Regular Expression`
- Improved validation when saving New URLs to avoid an edge case
- Updated barrelstrength/sprout-base-redirects requirement to v1.2.0
- Updated barrelstrength/sprout-base requirement to v5.0.8

### Fixed
- Fixed open redirect vulnerability (thanks to Liam Stein) ([#176][176-sprout-seo])
- Fixes bug where 404s could be matched before active redirects when matching regex URL patterns

[#6]: https://github.com/barrelstrength/craft-sprout-redirects/issues/6
[#7]: https://github.com/barrelstrength/craft-sprout-redirects/issues/7
[#10]: https://github.com/barrelstrength/craft-sprout-redirects/issues/10
[#16]: https://github.com/barrelstrength/craft-sprout-redirects/issues/16
[176-sprout-seo]: https://github.com/barrelstrength/craft-sprout-seo/issues/176

## 1.1.2 - 2019-08-16

### Changed
- Updated barrelstrength/sprout-base requirement to v5.0.7

## 1.1.1 - 2019-08-14

### Changed
- Updated barrelstrength/sprout-base-redirects requirement to v1.1.2

### Fixed
- Fixed js console warning when Craft is only configured with a single Site
- Fixed bug where incorrect return type hint was used

## 1.1.0 - 2019-08-06

### Added
- Added ability to sort Redirects by Count
- Added hard delete support for Redirect Elements

### Changed
- Sprout Redirects Lite now is full featured with a limit of 3 Redirect Rules
- Updated 'All Redirects' Element index listing to only show 301 and 302 Redirects, and exclude 404 Redirects
- Improved performance of Delete 404 task during large cleanup tasks 
- Updated barrelstrength/sprout-base-redirects requirement to v1.1.1

### Fixed 
- Fixed bug where 404 Redirect cleanup job was not working
- Fixed bug where Redirects could be double counted if SEO and Redirect plugins were both installed

## 1.0.2 - 2019-06-17

### Fixed
- Fixed invalid message category ([#11])

[#11]: https://github.com/barrelstrength/craft-sprout-redirects/issues/11

## 1.0.1 - 2019-04-28

### Changed
- Updated barrelstrength/sprout-base-redirects requirement to v1.0.10

### Fixed
- Improved Postgres support

## 1.0.0 - 2019-04-24

### Added 
- Initial release
