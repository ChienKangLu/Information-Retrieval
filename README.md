# Information-retrieval
This is my final project of **information retrieval** in college. In this project, we have already compared **Standard Boolean Model**, **Extended Boolean Model** and **Vector Space Model** for the task of searching chinese keywords and listed the advantage and drawback respectively.

## Standard Boolean Model
If we use this query to search documents,
```
羽球AND ( 全民OR運動OR比賽 ) AND推廣
```
There are three related documents retrieved by Standard Boolean Model:
<p>
<img height="200" src="https://github.com/ChienKangLu/Information-Retrieval/blob/master/Standard%20Boolean%20Model%20example/Standard%20Boolean%20Model1.jpg" />
  
<img height="200" src="https://github.com/ChienKangLu/Information-Retrieval/blob/master/Standard%20Boolean%20Model%20example/Standard%20Boolean%20Model2.jpg" />

<img height="200" src="https://github.com/ChienKangLu/Information-Retrieval/blob/master/Standard%20Boolean%20Model%20example/Standard%20Boolean%20Model3.jpg" />
</p>

+ Advantage
  + The result is predictable and easy to interpreted
  + It can contain many logic of keywords
  + Without calculate in advance, it can use bigram directly
+ Drawback
  + The effeciveness is greatly depended on how user design the boolean query
  + For simplt query, it will retrieve to many unrelated documents
  + Complext query is too difficult to designed by user
  
## Extended Boolean Model
If we use this query to search documents,
```
羽球AND ( 全民OR運動OR比賽 ) AND推廣
```
We can still get these three documents but the **hit** is only one for each document.
<p>
<img height="200" src="https://github.com/ChienKangLu/Information-Retrieval/blob/master/Extended%20Boolean%20Model%20example/Extended%20Boolean%20Model%20exp1.png" />
  
<img height="200" src="https://github.com/ChienKangLu/Information-Retrieval/blob/master/Extended%20Boolean%20Model%20example/Extended%20Boolean%20Model%20exp2.png" />

<img height="200" src="https://github.com/ChienKangLu/Information-Retrieval/blob/master/Extended%20Boolean%20Model%20example/Extended%20Boolean%20Model%20exp3.png" />
</p>

+ Advantage
  + It may find better document corresponding to the query because it use the sentence as unit
+ Drawback
  + It is so strict that it can not find any documents

## Vector Space Model
We calculate **term frequency (tf)** and **inverse document frequency (idf)** for each bigram first. Next, we wull calculate the **tf-idf weighting**.
+ **term frequency (tf)**: More frequent terms in a document are more important,<br/>

  <p align="center">
  <img src="https://latex.codecogs.com/svg.latex?f_i_j%20%3D%20%24%20frequency%20of%20term%20%24%20i%20%24%20in%20document%20%24%20j" />
  </p>
  normalize term frequency in the document,<br/>
  <p align="center">
  <img src="https://latex.codecogs.com/svg.latex?tf_i_j%20%3D%20f_i_j/max_i%5C%7B%7Bf_i_j%7D%5C%7D" />
  </p>
+ **inverse document frequency (idf)**: Terms that appear in many different documents are less indicative overall topic,<br/>
  <p align="center">
  <img src="https://latex.codecogs.com/svg.latex?%5Cbegin%7Bmatrix%7D%20df_i%26%20%3D%26%24document%20frequency%20of%20term%20%24i%20%5C%5C%20%26%20%3D%26%20%24numberof%20documents%20containing%20term%20%24i%20%5C%5C%20idf_i%20%26%20%3D%20%26%20%24inverse%20document%20frequency%20of%20term%20%24%20i%20%5C%5C%20%26%20%3D%20%26%20log_2%5C%28N/df_i%5C%29%20%5Cend%7Bmatrix%7D" />
  </p>
  Log is used to dampen the effect, *N* is total number of documents.
+ **tf-idf weighting**: A term occurring frequently in the document but rarly in the rest of documents is given high score,
  <p align="center">
  <img src="https://latex.codecogs.com/svg.latex?w_i_j%3Dtf_i_j%20idf_i%20%3D%20tf_i_jlog_2%5C%28N/df_i%20%5C%29" />
  </p>

  
  


