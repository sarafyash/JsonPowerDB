# ***JsonPowerDB***

## Introduction 
JsonPowerDB **(JPDB)** is a database server offering REST API services for developers. It's a Real-time database which provides high-performance and is light-weight, Ajax-enabled, serverless, and simple to use.
JsonPowerDB is equally Easy and Fast when used with Server Side programming like Java, .NET, Python or PHP etc.


## Features of JsonPowerDB 

* JPDB is nimble, simple to use, in memory and real time.
* JPDB is schema free and is quite easy to maintain.
* JPDB provides serverless support for fast development and cuts time to market.
* JPDB is built around the world's fastest indexing engine PowerIndex.
* Has a webservices API and has a  low development cost.
* JPDB has multiple security layers.
* A single instance - Million Indexes.
* Inbuilt support for querying multiple databases.
* Serverside Native NoSQL - best performance.
* Multi-mode database - One solution to a variety of data.
* Minimizes Total Cost of Ownership.
* Maximum Data processing performance.
* Fills gaps from Database to Big-data.
* Pluggable with new Algorithms.

## Use Cases of JsonPowerDB 

* Any software application that needs backend DB.
    * Dynamic web-apps/Mobile/Desktop Apps.
* All RDBMS Use cases.
* All key-value Use cases.
* All document Use cases.
* Use cases which needs Time series/geospatial analytics.
* Real time application for data analytics.
* Live working HTML templates.

<img src="C:\Users\saraf\Desktop\Screenshot 2022-06-01 131157.png" alt="Alt text">

## JsonPowerDB API Commands

>IML (JsonPowerDB Index Manipulation Language) for Inserting , Deleting/Removing and Updating a record in Json data.


* **Http method : POST**
* **Base url : http://api.login2explore.com:5577**
* **End-point url : /api/iml**

### 1. PUT Command
#### Syntax of PUT Command
```HTML
{
    "token": <"connection-token">,
    "cmd": "PUT",
    <<"dbName": <"database-name">,>>
    <<"rel": <"relation-name">,>>
    <<"colsAutoIndex": <boolean-value>,>>
    <<"templateStr": <json-template-data>,>>
    "jsonStr": <json-data>
}
```
### 2. UPDATE Command
#### Syntax of UPDATE Command

```HTML
{
    "token": <"connection-token">,
    "cmd": "UPDATE",
    <<"dbName": "database-name",>>
    <<"rel": "relation-name",>>
    "jsonStr": {
        <"record-no">: {
            <"column-name">: <"new-value">
        }
        <"record-no">: {
            <"column-name">: <"new-value">
        }
    }
}
```

### 3. Remove Command
#### Syntax of Remove Command

```HTML
{
    "token": <"connection-token">,
    "cmd": "REMOVE",
    <<"dbName": <"database-name">,>>
    <<"rel": <"relation-name">,>>
    "record": <record-number | [record-number1,...],>
    "jsonStr" : {}
}
```

>IRL (JsonPowerDB Index Retrieval Language) - For Retrieve Json data.


* **Http method : POST**
* **Base url : http://api.login2explore.com:5577**
* **End-point url : /api/iml**

### 4. GET Command
#### Syntax of GET Command

```HTML
{
    "token": <"connection-token">,
    "cmd": "GET",
    "dbName": <"database-name">,
    "rel": <"relation-name">,
    "jsonStr": {
        <"column-name">:<"column-value">
    }
}
```

### For More Json API Commands please visit - ***https://login2explore.com/jpdb/docs.html***
