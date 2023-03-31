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

## Proc json
```sas
/* define the path to the JSON file */
%let json_file = /path/to/your/json/file.json;

/* use proc json to read the json file */
proc json in="&json_file."
          out=mydataset;
     /* define the path to the desired information */
     read features/coordinates=coordinates
                   properties/formattedAddress=formatted_address
                             locality=locality
                             postalCode=postal_code
                             addressLine=address_line;
run;

/* print the contents of the output dataset */
proc print data=mydataset;
run;
```
