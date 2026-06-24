# Goodreads Books Dataset - SQL Exploratory Analysis

## Overview
An exploratory analysis of a Goodreads books dataset using SQL (via duckdb) to uncover patterns in ratings, page counts, author productivity, and book popularity. The project also identifies hidden gems (highly rated but low-visibility books) and overhyped titles (widely rated but underperforming on score).

## Questions Explored
- What is the most common page count range, and does length affect ratings?
- Which authors have the most books, and which have the highest average ratings?
- Which books are hidden gems — high quality but low visibility?
- Which books are overhyped — widely reviewed but rated poorly?

## Key Findings
- Medium-length books (201–400 pages) are the most common, but surprisingly, books over 700 pages have the highest average ratings — though the difference across ranges is small
- Page count has little overall effect on reader ratings
- Hidden gems and overhyped titles were identified using quantile-based filtering to avoid unreliable conclusions from books with very few reviews

## Data Cleaning Highlights
The dataset required significant cleaning before analysis:
- Removed books with 0 pages and entries flagged as "NOT A BOOK"
- Merged five English language codes (en-US, en-CA, en-GB, eng, enm) into a single "eng" category
- Filtered out titles with fewer than 50 ratings to improve reliability
- Special duplicates handling — it was necessary to identify that different editions of the same title (e.g. different translations, publishers, years) are valid separate entries, and used a multi-column deduplication strategy (title + author + publisher + date + language) rather than title alone

## Tools & Libraries
- Python (pandas, duckdb)
- SQL (via duckdb)
- Tableau (rating distribution and page range visualisations)

## Dataset
[Goodreads Books Dataset — Kaggle](https://www.kaggle.com/datasets/jealousleopard/goodreadsbooks)
