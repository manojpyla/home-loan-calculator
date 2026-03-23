# Web Scraper

A Python command-line tool that scrapes a webpage and exports structured data to an XML file.

## What It Does

The scraper fetches a given URL and extracts the following content into a structured XML file:

- Page title
- Meta tags (name and content)
- Headings (h1 through h6)
- Paragraphs
- Links (href and text)
- Images (src and alt)
- Tables (rows and cells)

After scraping, it prints a summary of the extracted data to the console.

## Requirements

### Environment

- **Python** 3.8 or higher (uses `xml.etree.ElementTree.indent`, introduced in Python 3.9)
- **OS:** Windows, macOS, or Linux

### Packages

Install the required third-party packages:

```bash
pip install requests beautifulsoup4
```

| Package          | Purpose                          |
|------------------|----------------------------------|
| `requests`       | HTTP requests to fetch webpages  |
| `beautifulsoup4` | HTML parsing and data extraction |

## Usage

### Interactive mode (prompts for URL and output file name):

```bash
python web_scraper.py
```

### With command-line arguments:

```bash
# Uses default output file (scraped_data.xml)
python web_scraper.py https://example.com

# Specify a custom output file
python web_scraper.py https://example.com --output result.xml
```

### Options

| Argument         | Description                                      |
|------------------|--------------------------------------------------|
| `url`            | URL of the webpage to scrape (optional at CLI)   |
| `--output`, `-o` | Output XML file path (default: `scraped_data.xml`) |

## Output

The script generates an XML file with the following structure:

```xml
<?xml version='1.0' encoding='utf-8'?>
<scraped_data url="https://example.com">
  <title>Example Domain</title>
  <headings>
    <heading level="1">Example Domain</heading>
  </headings>
  <paragraphs>
    <p>This domain is for use in illustrative examples...</p>
  </paragraphs>
  <links>
    <link href="https://www.iana.org/domains/example">More information...</link>
  </links>
</scraped_data>
```
