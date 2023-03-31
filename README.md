# geojson
```sas
/* define the path to the geojson file */
%let geojson_file = /path/to/your/geojson/file.geojson;

/* use proc geojson to read the geojson file */
proc geojson datafile="&geojson_file.";
run;
```

```sas
/* define the path to the geojson file */
%let geojson_file = /path/to/your/geojson/file.geojson;

/* use proc geojson to read the geojson file */
proc geojson datafile="&geojson_file."
     outfeat=features;
     /* define the output dataset and variables */
     output out=mydataset(drop=id) 
            coordinates=coordinates
            formatted_address=formatted_address
            locality=locality
            postal_code=postal_code
            address_line=address_line;
run;

/* print the contents of the output dataset */
proc print data=mydataset;
run;
```
