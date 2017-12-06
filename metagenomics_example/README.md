# Implementation of the  GA4GH schema based on metagenomics data

This folder contains data and information regarding the metagenomic implementation of a GA4GH schema structure.
This project aims to demonstrate the feasibility of such an approach, mainly to help the development of the scheme.

### Origin of the data


Example based on the ENA study PRJEB23107

URL : https://www.ebi.ac.uk/ebisearch/search.ebi?query=PRJEB23107&submit=&db=allebi&requestFrom=global-masthead 


### Structure

### How to import the data

```
mongoimport --db metagenomics --collection individuals --drop --file Metagenomic_Individual.json --jsonArray
mongoimport --db metagenomics --collection biosamples --drop --file Metagenomic_Biosample.json --jsonArray
mongoimport --db metagenomics --collection species --drop --file Metagenomic_NCBI.json --jsonArray
mongoimport --db metagenomics --collection assignsets --drop --file Metagenomic_Assignment.json --jsonArray
```


### Data manipulation with MongDB shell

Example of MongoDB query : 

```
use metagenomics
db.assignsets.find({"node_name":"Gemmatimonas" },{"biosample_id":1,"_id":0})
db.biosamples.find({"bio_characteristics.description":"arthritis"})
db.assignsets.find({"node_name":"Roseburia faecis","values.count" : {$gt:10000 }})
```


### Web server

A web interface based on beacon UI is available to explore these data 

URL : https://services.cbib.u-bordeaux.fr/beacon-metagenomic/ 











