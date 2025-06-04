# Enhanced Search-Engines-Scraper for EasyApply.co

This project is an enhanced version of the original [Search-Engines-Scraper](https://github.com/tasos-py/Search-Engines-Scraper) specifically optimized for comprehensive scraping of EasyApply.co job board sites.

## Overview

The original Search-Engines-Scraper was encountering pagination issues where Bing would return the same 10 results on every page. This enhanced version addresses those issues and successfully discovers significantly more results.

## Key Improvements

### 1. Fixed Base64 Decoding Error
- **Issue**: Original library had Base64 decoding errors in `search_engines/engines/bing.py`
- **Solution**: Added proper error handling and fallback mechanisms

### 2. Improved Pagination Handling
- **Issue**: Same results appearing on multiple pages due to bot detection
- **Solution**: Direct HTTP requests with proper Bing pagination parameters (`first` parameter)

### 3. Enhanced Bot Detection Avoidance
- Better browser simulation with comprehensive headers
- Session persistence for maintaining search context
- Random delays between requests

## Results Summary

- **Original method**: 18 unique easyapply.co URLs
- **Enhanced method**: 102 unique easyapply.co URLs (**467% increase**)
- **Organizations discovered**: 73 different companies using EasyApply platform

## Usage

### Quick Start - Improved Scraper
```bash
python improved_bing_scraper.py
```

### Consolidate Results
```bash
python consolidate_improved_results.py
```

## Files

### Core Scrapers
- `improved_bing_scraper.py` - Main enhanced scraper with multiple search strategies
- `incremental_bing_scraper.py` - Incremental saving version
- `comprehensive_scraper.py` - Multi-strategy scraper using the original library

### Utility Scripts
- `consolidate_improved_results.py` - Consolidates all CSV results into master file
- `test_failed_strategies.py` - Tests for library fixes

### Fixed Library Files
- `search_engines/engines/bing.py` - Fixed Base64 decoding issues

---

# Original search_engines Library  
_[BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)_  

## Installation  

Run the setup file: `$ python setup.py install`.  
Done!  

## Usage  

As a library:  

```
from search_engines import Google

engine = Google()
results = engine.search("my query")
links = results.links()

print(links)
```

As a CLI script:  

```  
$ python search_engines_cli.py -e google,bing -q "my query" -o json,print
```

## Other versions  

 - [async-search-scraper](https://github.com/soxoj/async-search-scraper) A really cool asynchronous implementation, written by @soxoj   
