"1. Create a bucket and upload the csv file"
"2. open cloudshell and upload the python pipeline file"
3. Install the virtualenv module, create a virtual environment, and then activate it:

pip3 install virtualenv
python3 -m virtualenv env
source env/bin/activate

4. Install Apache Bean
pip3 install apache-beam[gcp]

5. Run the pipeline
python3 csv_to_bigquery.py \
--input gs://sandeep-apache/data-flow-demo.csv \
--output  gs://sandeep-apache/out.txt \
--project techlanders-internal \
--region us-central1 \
--staging_location gs://sandeep-apache/staging \
--temp_location gs://sandeep-apache/temp \
--runner DataFlowRunner
