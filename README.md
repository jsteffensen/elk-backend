# elk-backend
## Setting up ElasticSearch and Kibana

Install ElasticSearch and Kibana according to https://www.elastic.co/downloads/elasticsearch

Run ElasticSearch:

cd into bin directory - and run `elasticsearch`

`C:\elasticsearch\elasticsearch-7.3.1\bin>elasticsearch`

cd into Kibana bin directory - and run `kibana`

`C:\kibana\kibana-7.3.1-windows-x86_64\bin>kibana`

## Creating indexes and sample data

In Kibana click the wrench button to go to Kibana console (http://localhost:5601/app/kibana#/dev_tools/console?_g=()).

To create the casefiles index via the Kibana console run:

`PUT /casefiles`

To insert a document into casefiles run:

```
POST casefiles/_doc/
{
    "user" : "KC6NS4",
    "case_type" : "root",
    "title" : "KC6NS4 root file",
    "parent" : ""
}
```

To update a document run:

```
POST casefiles/_update/2xx0LG0B8gaI_TxV63xc
{
    "doc" : {
        "title" : "KC6NS4 root"
    }
}
```

To search casefiles run:

```
GET casefiles/_search
{
    "query": {
        "match_all": {}
    }
}
```
