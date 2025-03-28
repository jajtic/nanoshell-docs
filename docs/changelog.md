# Nanoshell Changelog

All notable changes to nanoshell will be documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [0.1.7] - 2024-08-28

### Added
- added `linuxDistroName` to the nanoshell library

### Removed
- removed `systemScreenResolution` from the nanoshell library



## [0.1.6] - 2024-08-12

### Added
- added `systemScreenResolution` to the nanoshell library



## [0.1.5] - 2024-08-08

### Added
- nanoshell variables have been moved to the new nanoshell library (`nanoshell_lib-base.py`, `nanoshell_lib.py`)
    - includes: `versionStr`, `systemPlatform`, `addonCount`, `addonScriptCount`, `addonList`
    - `nanoshell_lib.py` is dynamically written by `run.py`



## [0.1.4] - 2024-07-22

### Changed
- simplified `platformWarning()` in `nanoshell-base.py`



## [0.1.3] - 2024-07-22

### Added
- "Command not found" message when unknown command is entered
- added `bright` to `coloramasetup.py`
- `run.py` now launches nanoshell.py using `python nanoshell.py` or `python3 nanoshell.py`, **depending on the platform**.
- user preferences such as the accent color are now stored in `config/preferences.json`, default preferences in `config/preferences_default.json`
- base file `coloramasetup-base.py`

### Changed
- post-load message was changed from `Finished, executing Nanoshell...` to `Finished, starting Nanoshell...`
- `run.py` now dynamically writes `coloramasetup.py` based on `preferences.json` (accentColor)
- phrased the platform warning a bit differently
- `"darwin"` is now a possible value as the system platform

### Fixed
- `run.py` now ignores non-directory files in addons folder to prevent any possible issues




## [0.1.2] - 2023-12-19

### Added
- `run.py` now checks addons' platform key
- platform warning (`nanoshell-base.py`) - warns if addon isn't supported on client platform

### Changes
- addon JSONs now require a platform key
- system platform is now checked in `run.py` (instead of `nanoshell-base.py`) and stored into variable **system_platform** in `nanoshell-base.py`

### Removed
- `"java"` is no longer a possible value as the system platform



## [0.1.1] - 2023-08-21

### Added
- platform checking in `nanoshell-base.py` (win/linux/java/unknown)
- added `light_green` to `coloramasetup.py`



## [0.1.0] - 2023-08-12 

### Added
- `coloramasetup.py` - simple library with colors
- more verbose messages in _run.py_

### Changed
- nanoshell version is now stored in a variable **versionStr** in _nanoshell-base.py_



## [0.0.1] - 2023-06-30

### Added
- Working nanoshell base and essential scripts