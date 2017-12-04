# Implementation of the  GA4GH schema based on metagenomics data

This folder contains data and information regarding the metagenomic implementation of a GA4GH schema structure.
This project aims to demonstrate the feasibility of such an approach, mainly to help the development of the scheme.

### Origin of the data


Example based on the ENA study PRJEB23107

URL : https://www.ebi.ac.uk/ebisearch/search.ebi?query=PRJEB23107&submit=&db=allebi&requestFrom=global-masthead 


### Structure

### How to import the data

### Data manipulation with MongDB shell

Example of MongoDB query : 

```
use metagenomics
db.biosamples.find({'attributes.country.values.string_value' : 'United Kingdom'})
db.biosamples.findOne({'description' : {'$regex' : 'breast'}})
db.variants.find({variant_type:"DEL", reference_name:"17", start:{$gte:30000000}, end:{$lte:31000000}},{"calls.call_set_id":1})
```



### Web server

A web interface based on beacon UI is available to explore these data 

URL : https://services.cbib.u-bordeaux.fr/beacon-metagenomic/ 











