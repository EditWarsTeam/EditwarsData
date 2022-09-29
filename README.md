## Edit Wars Project 
[Data based art research](https:/editwars.org), studying special aspects of Russian propaganda and media situation in Russia regarding the invasion in Ukraine 2022 and current war.

By using [GDELT Global Difference Graph (GDG)](https://blog.gdeltproject.org/announcing-the-gdelt-global-difference-graph-gdg-planetary-scale-change-detection-for-the-global-news-media/) databases, we analyzed more than 250,000 newsheaders of Russian-language media publications. We used machine learning tools (in particular, the [BERTopic algorithm](https://maartengr.github.io/BERTopic/index.html)) to thematically clusterize data and to obtain relevant topics with the dynamics of their change. Additionally, we also applied [Tableau](https://www.tableau.com) to discover typical words and phrases of propaganda. Finally, we extracted word connections in headlines and visualized the resulting network graph using [Spacy library](https://spacy.io).
***
### <b>Analysis</b>
Directory "Analysis" contains Ipynb-files with tools used to analyse database of media publications.

- <b>Clusters.ipynb</b>
<br>The open dataset GDELT Global Difference Graph (GDG) is used to make queries to extract titles of media in the Russian language. A request to database was created in [Google BigQuery](https://console.cloud.google.com/bigquery?sq=660327570123:bf28559e6ed1406fbb7e0eade9d762bc). <br>
Clusters.ipynb loads a cleared dataset df_result.csv with headlines from [Google Drive](https://drive.google.com/drive/folders/1lGJRJ0-v4RuN8ymzL5gLX8pjAfkBMfpU?usp=sharing), fits the clustering model using BERTopic and embedding SentenceTransformer model, tuns clusters using HDBSCAN, UMAP and CountVectorizer models, saves BERTopic model and topics.<br>
Clusters.ipynb collects info about topic in united DataFrame, gets data with all headlines in topics, visualises topics over time by narratives and a map of topics.


- <b>Words_connections.ipynb</b>
<br>It lemmatises words in headlines of relevant topics (all_headlines.csv) using Spacy lib, defines head and target words in sentences and saves to network_graph.csv.


- <b>Translate_words.ipynb</b>
<br> It translates dataset network_graph.csv to English language using [Google Cloud Translate API](https://cloud.google.com/translate).

***
### <b>Pre research</b>
Directory "Pre research" contains Ipynb-files with numbers of most popular words in headlines, images of wordclouds with slipping the time and K-Means clustering model. 
<br> Also it has Media_types.csv file based on manually categorisation for relevant and non-relevant media for research. 
