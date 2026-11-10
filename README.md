# Information Retrieval: Crawler and Search Engine

A Python project that follows the information-retrieval pipeline from collecting web pages to searching an index. It brings together crawling, text preprocessing, a database-backed inverted index and a local web interface.

## What to look at

- [crawl/](crawl/): crawling, document processing, indexing and query handling.
- [crawl/index.py](crawl/index.py) and [index.sql](index.sql): inverted-index construction and storage.
- [GUI/server_init.py](GUI/server_init.py): Flask interface returning ranked search results.
- [queries.txt](queries.txt) and [results.txt](results.txt): example batch queries and stored results.

**Stack:** Python, SQLite/APSW, NLTK and Flask. Start with the source and saved results for a quick review; running a new crawl requires network access and a populated local database.

## Usage

Crawler CLI:
```
python -m crawl.cli
```

Install requirements:
```
pip install -r requirements.txt
```

Download NLTK Corpora:
```
python -m crawl.cli download-corpora
```

Initialize crawler database & start crawling from the seed set:
```
python -m crawl.cli init-db
python -m crawl.cli load-urls
python -m crawl.cli crawl
```

Create the index from the crawler database:
```
python -m crawl.cli index-all
```

Query the index with a batch file:
```
python -m crawl.cli query
```

Serve the web interface locally:
```
python GUI/server_init.py
```
