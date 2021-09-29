# Elasticsearch

## What is Elasticsearch?

[Elasticsearch](https://www.elastic.co/products/elasticsearch) is an open source search engine built on top of [Apace Lucene](http://lucene.apache.org/).
Elasticsearch is distributed, which means that indices can be divided into shards and each shard can have zero or more replicas. All of its functionality is available through a RESTful API.


## Tutorials and Resources

  * [Official API documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/docs.html)
  * [Official Python client documentation](https://elasticsearch-py.readthedocs.io/en/master/)
  * Tutorials (mind that some of these might be outdated, i.e., are made for older ES versions)
    - http://www.elasticsearchtutorial.com/elasticsearch-in-5-minutes.html
    - http://joelabrahamsson.com/elasticsearch-101/
    - https://www.tutorialspoint.com/elasticsearch/index.htm


## Installing Elasticsearch

  * Download the latest Elasticsearch distribution from https://www.elastic.co/downloads/elasticsearch (currently: 7.15)
  * Unzip

## Running the service

  * Run `bin/elasticsearch` on Unix or `bin\elasticsearch.bat` on Windows to start the service
    * The service will run as long as you have that terminal window open; will need to be launched again upon machine restart, for example.

## Using Elasticsearch

You can use any tool/programming language to talk to Elasticsearch through a HTTP (RESTful) API.

See the [Jupyter notebook](Elasticsearch.ipynb) for a working Python example.

### From a browser

Go to `http://localhost:9200/`

![Elasticsearch from browser](images/elastic_browser.png)


### From the command line

Use curl

```
curl 'http://localhost:9200/'
```

![Elasticsearch from command line](images/elastic_curl.png)


### Using tools

There is a bunch of REST client tools.
E.g., [Postman](https://www.getpostman.com/) is available as Chrome App and also have a native Mac app; [here are some other alternatives](http://alternativeto.net/software/postman-google-chrome-extension-/).


### From Python

There is an [official python client](https://www.elastic.co/guide/en/elasticsearch/client/python-api/current/index.html) with [documentation](https://elasticsearch-py.readthedocs.io/en/master/) for that.

If you are using Anaconda, install it using:
```
conda install elasticsearch
```

Alternatively, it can be installed with pip:
```
pip install elasticsearch
```

Example use:
```
from elasticsearch import Elasticsearch

# by default we connect to localhost:9200
es = Elasticsearch()

es.info()

```


## Indexing Data

Uses the [Index API](https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-index_.html).

Based on [this example](http://www.elasticsearchtutorial.com/elasticsearch-in-5-minutes.html), we index blog posts where our index is called "blog".


### From the command line

Into a document into the "blog" index, with a document id of 1

```
curl -XPUT 'http://localhost:9200/blog/_doc/1' -d '
{
    "user": "dilbert",
    "postDate": "2011-12-15",
    "body": "Search is hard. Search should be easy." ,
    "title": "On search"
}'
```

If it was successful, it is confirmed by a message like:
```
{
  "_index": "blog",
  "_type": "_doc",
  "_id": "1",
  "_version": 1,
  "result": "created",
  ...
}
```

### From Python

```
DOCS = {
    "1": {
        "user": "dilbert",
        "postDate": "2011-12-15",
        "body": "Search is hard. Search should be easy." ,
        "title": "On search"
    },
    "2": {
      # ...
    }
    # ...
}

INDEX_NAME = "blog"

# Create index
if not es.indices.exists(INDEX_NAME):
    es.indices.create(index=INDEX_NAME)

# Add documents to index
for doc_id, content in DOCS.items():
    es.index(index=INDEX_NAME, doc_type="_doc", id=doc_id, body=content)
```

Note: use bulk indexing for large datasets.


## Get document content

We can request a given document based on its ID (e.g., to verify the content that got indexed) using the [Get API](https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-get.html).


### From the command line (or browser)

```
curl http://localhost:9200/blog/_doc/1?pretty=true
```

```
{
  "_index" : "blog",
  "_type" : "_doc",
  "_id" : "1",
  "_version" : 1,
  "_seq_no" : 0,
  "_primary_term" : 1,
  "found" : true,
  "_source" : {
    "user" : "dilbert",
    "postDate" : "2011-12-15",
    "body" : "Search is hard. Search should be easy.",
    "title" : "On search"
  }
}
```

### From Python

```
doc = es.get(index=INDEX_NAME, id=1)
```


## Index statistics

### From the command line (or browser)

```
curl http://localhost:9200/blog/_stats
```

```
{
  "_shards": {
    "total": 10,
    "successful": 5,
    "failed": 0
  },
  "_all": {
    "primaries": {
      "docs": {
        "count": 3,
        "deleted": 0
      },
...
}
```

### From Python

```
stats = es.indices.stats(index=INDEX_NAME)
```


## Search

Search is performed using the [Search API](https://www.elastic.co/guide/en/elasticsearch/reference/current/search-search.html).

In the example below, we search for documents (blog posts) that match the query "search distributed".

### From the command line (or browser)

See [search request from URI](https://www.elastic.co/guide/en/elasticsearch/reference/current/search-uri-request.html) page for the description of parameters.

```
curl 'http://localhost:9200/blog/_search?q=search+distributed&_source=false&pretty=true'
```

```
{
  "took": 3,
  "timed_out": false,
  "_shards": {
    "total": 1,
    "successful": 1,
    "skipped": 0,
    "failed": 0
  },
  "hits": {
    "total": {
      "value": 1,
      "relation": "eq"
    },
    "max_score": 0.39556286,
    "hits": [
      {
        "_index": "blog",
        "_type": "_doc",
        "_id": "1",
        "_score": 0.39556286
      }
    ]
  }
}
```

### From Python

```
query = "search distributed"
hits = es.search(index=INDEX_NAME, q=query, _source=False, size=10)['hits']
```
