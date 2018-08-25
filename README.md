# Information-retrieval
This is my final project of **information retrieval** in college. In this project, we have already compared **Standard Boolean Model**, **Extended Boolean Model** and **Vector Space Model** for the task of searching chinese keywords and listed the advantage and drawback respectively.

## Standard Boolean Model
If we use this query to search documents,
```
羽球AND ( 全民OR運動OR比賽 ) AND推廣
```
There are three related documents:
<p>
<img height="200" src="https://github.com/ChienKangLu/Information-Retrieval/blob/master/Standard%20Boolean%20Model%20example/Standard%20Boolean%20Model1.jpg" />
  
<img height="200" src="https://github.com/ChienKangLu/Information-Retrieval/blob/master/Standard%20Boolean%20Model%20example/Standard%20Boolean%20Model2.jpg" />

<img height="200" src="https://github.com/ChienKangLu/Information-Retrieval/blob/master/Standard%20Boolean%20Model%20example/Standard%20Boolean%20Model3.jpg" />
</p>


+ Advantage
  + The result is predictable and easy to interpret
  + It can contain many logic of keywords
  + Without calculate in advance, it can use bigram directly
+ Drawback
  + The effeciveness is greatly depended on how user design the boolean query
  + For simplt query, it will retrieve to many unrelated documents
  + Complext query is too difficult to designed by user
