# KIBANA DASHBOARD

This project helps to get live tweets on [kibana](https://www.elastic.co/guide/en/kibana/current/dashboard.html) dashboard. 

This solution helps you to listen to keywords (similar to twitter search for keywords) and stream related tweets in near real time onto Kibana Dashboard. 

Requirements:
1. ElasticSearch and Kibana
2. Python 3.6 + ElasticSearch and Tweepy Python APIs
3. Machine to host the above.

Steps to deploy the solution:
1. Setup ElasticSearch and Kibana in the host machine.
2. Make necessary configurations in Python code and run it in the host machine.
	The python code here is well commented and the user just has to make necessary changes in places we have *** (Make sure you fill everything) . The user just has to provide twitter developer keys ([link](https://apps.twitter.com/)) and ElasticSearch credentials for above server. Provide lsit of keywords to stream related tweets.
	
3. Create Kibana dashboards.
4. 
1. Setup ElasticSearch and Kibana in the host machine
Refer to, https://www.elastic.co/guide/en/elasticsearch/reference/current/install-elasticsearch.html

2. 
~~~~
- ElasticSearch package  used to get the data from twitter.
- tweepy python library could be used for accessing the Twitter API.
- json package coud be used to work on JSON data. JSON string can be parsed it by using the json.loads() method.
~~~~


Keywords related to problem statement could be added in index in the code  and add the code in [ElasticSearch](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html) to fetch the live tweets.

For example, 
- kerala flood: savekerala
- disease: leptospirosis
- symptoms: fever


# How to create Kibana dashboard:

* Downloading, prerequisites, and running Elasticsearch in the local system. 
* After installing ElasticSearch, cluster with one node will be running. You can interact with it at http://localhost:9200/
* You can create another node as well which is quite simple, using the command: **bin/elasticsearch - Des.node.name=Node-2**
* By default we will be able to communicate with this new node using the 9201 port http://localhost:9201.
* Pip install the packages mentioned above in command prompt. 
* Add python code to the cluster in ElasticSearch.
* Download and install Kibana in the local system.

Code was built that would fetch the tweets from twitter and display on Kibana dashboard.

# Steps for coding:

1. Load all the packages (elasticsearch, tweepy, json) in code. 
2. Create an index using fuunction, es.indices.create(index = <index_name>) 
3. Create mapping specifying what fields would be present in each record of index.
4. Using function, es.indices.put_mapping("tweets", {'properties':mapping}, [INDEX_NAME]), it updates mapping or schema of the documents in the index
5. Create twitter API:
	- Go to the link: https://apps.twitter.com/
	- Sign in to the account and apply for developer account and get: 
	* consumer_key
        * consumer_secret
        * access_token
        * access_token_secret
6. Enter the keys and secrets credentials given by Twitter.
7. Create a class StdOutListener and define fucntion in it.
8. Call class and also mention the keywords in function.

The entire code could be found [here](https://github.com/NishaSingh07/demo-repo/blob/master/twitter_streaming_refined.py).
