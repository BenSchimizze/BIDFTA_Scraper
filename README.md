# BIDFTA_Scraper
## Usage

**Create new Bidfta class. On init, parses the main BIDFTA website.**

```
bid = Bidfta()
```

**Default includes all auction sites. Invoke method cincy_only() to reduce auctions to only Cincinnati**

```
bid.cincy_only()
```

**Optional method prints all base auction CGI's**

```
bid.print_all_loc()
```

**Method parse_auctions() crawls thru auction dictionary and publishes to an SQLite db. Returns open SQLite cursor for search**

```
c = bid.parse_auctions()
```

**Example search function**
```
c.execute("""SELECT * FROM items 
             WHERE description like '%drone%'
             ORDER BY msrp desc
            """)
c.fetchall()```
