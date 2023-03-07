# macrometa-akamai-simplekv

This is a simple walk-through for a demo of creating a simple, document key-value database on Macrometa's CDN, and then accessing the database contents via Macrometa's Global API.

## Wny Macrometa?

Macrometa is a leader in providing distributed databases, with numerous data interaction models (API, SDK, streaming, pub/sub), as well as FaaS modules for allowing the manipulation and processing of that data. In effect, Macrometa is both a global Database as well as Application/Function as a service platform. 

Their studio environment and developer tools make it easy to get started with globally distributed databases in a manner of minutes. The purpose of this demo is to show exactly how easy that is.

## Getting Started

1. Sign up for a Macrometa account- their free tier will work fine for this demo.

2. Login to the Macrometa playground via the "login" link on the macrometa.com homepage.

## Creating a document KV database

1. From the Playground homepage, choose "Collections" in the left-hand nav.

2. You should see some default collections present. Select "New Collection" at the top.

3. Select "Document Store" as the type of collection you want to create. From there, name the collection, and choose "Global" as Geo-Replication type. Click on "Create" - you then should see your new collection in the list. 

## Adding Data to your new document DB

1. Click on the name of your new collection in the list, and you'll then see the details page for that collection. The key/data list should be empty.

2. To add documents to the database, select the down arrow button at top - "Import Documents from Json File." From there, select the test1.json file included in this repository.

3. You should then see a list of keys/documents now saved in the Collection.

## Accessing the data via Macrometa API

### Create an API Key

1. From the left hand menu, select "Account." This should bring you to the Account page. From there, at the top, select "Create New API Key." Give the key a name, and copy the value of the key once shown. 

###  Test the API Endpoint and Key

1. From the left hand menu, Select "API Reference." From the first screen, select "Use API Key" on the right hand side, and enter the API key you created.

2. From here, you can obtain the API endpoint for your database, as well as sample commands to interact with your data. 

Below is a sample API call to retrieve a json from a document database in Macrometa GDN-

```
curl -X 'GET' \
  'https://api-bonytail-d58de20f-us-east.paas.macrometa.io/_fabric/_system/_api/document/Asd/2' \
  -H 'accept: application/json' \
  -H 'Authorization: apikey TiVLAbP8zRYmWczcLZ361Qw.test.EF1mv0oZPr00WFsJN82QHn5J15nRxJDAY9brG5Y3wk22tyimDaCJ6mREOQeSEfLS8bf910'
  ```
