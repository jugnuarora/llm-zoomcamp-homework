__Step 1: ENV__ Setting up the environment
```
pip install tqdm notebook==7.1.2 openai elasticsearch==8.13.0 pandas scikit-learn ipywidgets
```
__Step 2:__ Create `.env` file with OPENAI_API_KEY. Make sure it is in your .gitignore also.

__Step 3: ELASTICSEARCH__ Run ElasticSearch:
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

__Step 5:__ Fetch the documents and flatten it by running the code given in homework.

__Step 6:__ Run Elasticsearch in docker

__Step 7: INDEXING__ Do the index setting as to which will be text columns and which will be keyword. Create the index with these settings

__Step 8:__ Add the documents to index.

__Answer 2: index__

__Step 9: SEARCHING__ Write the search query and select fields, apply boost. Use `.search`method to get the response for query.

__Step 10: Max Score__ `response['hits']['max_score']`to get the score of top ranking result

__Answer 3: 44.50__

__Step 11: Filtering__ Re-write the search query and change the `size`to 3. Also use `filter`to filter on `machine-learning-zoomcamp`

__Step 12:__ To check the questions for each returned response use `response['hits']['hits']``

__Answer 4: How do I copy files from a different folder into docker container’s working directory?__

__Step 13:__ Build the context using the returned searched documents

__Step 14:__ Build the prompt_template.

__Step 15:__ format the prompt_template to create the actual prompt

__Step 16:__ len(prompt)

__Answer 5: 1446__

__Step 17:__ Import tiktoken and encode the prompt generated. Then use len() to find the number of tokens generated.

__Answer 6: 320__

__Step 18:__ I have saved OPENAI_API_KEY in .env file and retrieved it using dotenv module.

__Step 19:__ Create 3 functions
    (a) Get the search results from the documents
    (b) Build the prompt
    (c) Send the prompt to llm to retrieve the answer

__Step 20:__ Create a function that encompasses all the above 3. And call this function with the query.

__Step 21:__ We are sending 320 tokens and recieving 62 tokens thus the total cost is $2.53