# Changelog

## V 1.2.1
## Fixed
 - Fixed Bittrex `deposit_address()` per PR #72
 - Fixed Cryptopia's currencies per PR #71
 - Fixed Cryptopia's signature method #69
 - Fixed missing encoding in GDAX authorization

## Added
 - Implemented Kraken's`wWithdraw()` and `deposit_address()` per PR #70

## V 1.1.0
### Added
Exchanges:
- HitBTC API Client & Interface
- Bter API Client & Interface
- Vaultoro API Client & Interface

APIs:
- The Following Exchanges had their WSS API implemented:
    - HitBTC
    - GDAX
    - Bitfinex
    - Bitstamp
    - Gemini
    - Poloniex[Beta]
    - OkCoin
    
### Changed
Project Structure
- `bitex.api` now features 2 submodules, `REST` and `API`. This should
not affect any imports in existing code.

### Deprecated
### Removed
### Fixed
Various spelling errors

## V 1.0
### Added
General:
- Changelog (Yay!)
- Pip install support
- Semantic versioning now employed.
- Added folder for Sphinx doc files, for hosting at ReadTheDocs
- Added folder for Unittests; so far only tests for API classes exist

Exchanges:
- Poloniex  API Client and interface
- Interfaces for all API Client currently implemented
- Standardized methods with identical method headers for all interfaces
- Quoine API Client and interface
- QuadrigaCX API Client and interface

Formatters:
- The sub-module `bitex.formatters` has been added, which provides formatter
functions for exchange interfaces.

### Changed
General:
- Restructured project to store interfaces in `bitex.interfaces` sub-module

API Clients
- The base class `RESTAPI` has been renamed to `APIClient` to better reflect
its purpose
- The class `APIClient` is now an ABC
- The attribute `request_methods` has been removed and its logic and purpose
replaced by using `requests.request()` instead.

Exchanges:
- All calls to interface methods now return an `APIResponse()` object; this is a
subclass of `requests.Response` and adds an attribute `formatted` - which
contains formatted json data, if available.
- Bitstamp's `tickers` method had its surplus `s` removed.

### Deprecated
- btc-e API is no longer supported actively.

### Removed

### Fixed
- Various spelling and code errors which resulted in the code crashing in unexpected situations.
