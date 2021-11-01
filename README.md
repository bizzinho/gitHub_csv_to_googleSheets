# testGoogle
Testing reading csv from github to google sheet

Turns out this is easy to do. For public repos, the raw link to a csv file can be imported by google sheets via importdata. 

If one wants to use sorting by different colors, one can do sth like this:
```
=QUERY(IMPORTDATA("<github_raw_link>"), CONCATENATE("SELECT * ORDER BY ",IF(D2="<columnA_name>","Col1", "Col2"), IF(D3="ascending", " asc"," desc")), 1)
```

Where the underlying data structure is a table with two columns with one header row; two separate fields (D2 and D3 in the example) contain cells with data validation 
that are used to control the sorting.
