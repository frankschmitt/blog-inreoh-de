---
title: 'PostgreSQL cheatsheet'
layout: post
published: true
categories: postgresql
tags: postgresql cheatsheet
---

# Synopsis
Simple cheatsheet for PostgreSQL (will grow over time)

## Connect to DB
```
psql -U <username> -d <database>
```

## Export a table as csv
```
\COPY products_273 TO '/tmp/products_199.csv' WITH (FORMAT CSV, HEADER);
```
Note the backslash before COPY; this allows you to run the command as a non-privileged user. For further info, see 
[SO PostgreSQL export to CSV|https://stackoverflow.com/questions/1120109/export-postgresql-table-to-csv-file-with-headings#1120390]

