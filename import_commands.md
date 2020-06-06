
# To load the database

```
sudo neo4j-admin import --database=sdm1.db --nodes:journal journal.csv \
									       --nodes:conference conference.csv \
										   --nodes:author author.csv    \
										   --nodes:article article.csv   \ 
										   --nodes:keyword keywords.csv   \ 
										   --relationships:writes author_writes.csv    \
										   --relationships:reviews author_reviews.csv    \
										   --relationships:published_inj journal_published_in.csv    \
										   --relationships:published_inc conference_published_in.csv \
										   --relationships:has article_keywords.csv \
										   --relationships:cited_by citations.csv \
										   --ignore-missing-nodes=true
```


# To make it accesible via the web interface of neo4j
					   
`sudo chown -R neo4j:adm /var/lib/neo4j/data/databases/sdm1.db/`

# To see it in the browser edit /etc/neo4j/neo4j.conf

```
vi /etc/neo4j/neo4j.conf
# set dbms.active_database
dbms.active_database=sdm1.db

# and restart the service
sudo service neo4j restart
```

One-line commands examples. (For some reason I have different names for some relationships)

```
sudo neo4j-admin import --database=sdm1_v2.db --nodes:journal journal.csv --nodes:conference conference.csv --nodes:author authors.csv  --nodes:article articles.csv --nodes:keyword keywords.csv --relationships:writes author_writes_article.csv  --relationships:reviews author_reviews.csv --relationships:published_in journal_published_in.csv --relationships:published_in conference_published_in.csv --relationships:has article_keywords.csv --relationships:cited_by citations.csv --ignore-missing-nodes=true

sudo neo4j-admin import --database=sdm1_v1.db --nodes:journal journal.csv --nodes:conference conference.csv --nodes:author authors.csv  --nodes:article articles.csv --nodes:keyword keywords.csv --relationships:writes author_writes_article.csv  --relationships:reviews author_reviews.csv --relationships:published_in journal_published_in.csv --relationships:published_in conference_published_in.csv --relationships:included_in article_keywords.csv --relationships:cited_by citations.csv --ignore-missing-nodes=true
```
