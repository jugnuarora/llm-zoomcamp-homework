__Step 1:__ Setting up the environment
```
pip install tqdm notebook==7.1.2 openai elasticsearch==8.13.0 pandas scikit-learn ipywidgets
```
__Step 2:__ Create `.env` file with OPENAI_API_KEY. Make sure it is in your .gitignore also.

__Step 3:__ Run ElasticSearch:
````
docker run -it \
    --rm \
    --name elasticsearch \
    -m 4GB \
    -p 9200:9200 \
    -p 9300:9300 \
    -e "discovery.type=single-node" \
    -e "xpack.security.enabled=false" \
    docker.elastic.co/elasticsearch/elasticsearch:8.17.6
````
__Step 4:__ Execute the following to retrieve the version build_hash value
````
curl http://localhost:9200
````

__Answer 1: "dbcbbbd0bc4924cfeb28929dc05d82d662c527b7"__

__Step 5:__ 

