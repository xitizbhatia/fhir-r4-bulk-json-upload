# fhir-r4-bulk-json-upload
Script to do FHIR bulk upload JSON files to FHIR R4 Server (e.g. HAPI FHIR JPA Server)

Run the HAPI FHIR JPA Server in R4 mode.

Download 1K Sample Synthetic Patient Records, FHIR R4: 81 MB from https://storage.googleapis.com/synthea-public/synthea_sample_data_fhir_r4_sep2019.zip

Unzip the downloaded zip file.
Then in command line, navigate to the folder containing the JSON files.

Run the command:

find . -type f -exec curl -X POST -H "Content-Type:application/fhir+json;charset=utf-8" --data @{} "http://server:port/hapi-fhir-jpaserver/fhir/" \;

Replace the http protocol, server, port and context path to match your setup.
This will upload all the JSON files into your FHIR R4 server.
