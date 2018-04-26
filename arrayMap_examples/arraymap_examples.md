## arrayMap examples

The files in this directory show examples for the representation of genomic and metadata from the [arrayMap](http://arraymap.org) cancer genome repository, using the [GA4GH metadata schema](http://ga4gh-metadata.github.io). These examples are direct excerpts from the MongoDB collections behind the [Beacon+](http://beacon.progenetix.org) implementation.

Apart from the metadata, these examples represent genomic variants in the following form:

#### Precise variants (SNV...):

```json
{
	"_id" : ObjectId("5a9d039509d374772330c391"),
	"digest" : "1:43447122-43447122:C=>T",
	"variantset_id" : "tcga_ga4gh_vs_GRCh38",
	"reference_name" : "1",
	"start" : 43447122,
	"end" : 43447122,
	"reference_bases" : "C",
	"alternate_bases" : [
		"T"
	],
	"variant_type" : "SNP",
	"genotype" : [
		0,
		1
	],
	"callset_id" : "14b7d726-410a-4847-83d0-ba01ffc3336c_6b99c1ba-83d1-4636-bb8d-b1dccaca6afe",
	"biosample_id" : "30822e80-8ef8-4ac9-af5d-304aa7f8c1dd",
	"info" : {		
	},
	"updated" : "2018-03-05T08:45:09Z"
}
```

#### Structural variants (DUP, DEL...):

```json
{
	"_id" : ObjectId("5a9d0b0e09d374772366d106"),
	"digest" : "1:3301765-54148736:DUP",
	"variantset_id" : "tcga_ga4gh_vs_GRCh38",
	"reference_name" : "1",
	"start" : 3301765,
	"end" : 54148736,
	"reference_bases" : ".",
	"alternate_bases" : [
		"<DUP>"
	],
	"variant_type" : "DUP",
	"genotype" : [ ],
	"callset_id" : "c5c4b4a3-3224-4a72-a883-c99c7747e47b",
	"biosample_id" : "44992adb-cabf-4c2f-9f3b-45cf97531319",
	"info" : {
		"value" : 0.4242,
		"svlen" : 50846971,
		"probes" : 27221
	},
	"updated" : "2018-03-05T09:17:02Z"
}
```