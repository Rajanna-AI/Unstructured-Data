# ProText makes your Text Preprocessing & Feature extraction tasks easy for NLP applications

A Helper pip package for text prepocessing & feature extraction. 

This pip package helps you execute **text cleaning** like 

   + General cleaning (Removal of URL, @username, addtional whitespaces, Hashtags, punctuations..etc)
   + Stopword removal
   + Adding more stop words to "stopwords.words" library list
   + Stemming, 
   + lemmatiing, 
   + Removal of single or two character word, 
   + Converting to lower case,
   + Removal of digits
   + Spell correction
   + Creating of Wordcloud & line graph

All of these can be executed in a single line of command sequentially in any prefered order or can be executed in multiline.

Also feature extrations like **CountVectorizer & TfidfVectorizer**

> Package can be executed on both panda DataFrames and single line of text

This tool can be really helpful and No one neither needs to rememebr various syntax associated with processing nor packages.

This packages reuses functions from nltk, Textblob and wordcloud for the above operations.

### Assumptions:
   - Assuming python is installed on your system.
   - nltk, Textblob and wordcloud installed on your system

Install `ProText` on your system using :

   ``` 
    pip install ProText 
   ```

## Text Preprocessing user guide on df or text

   + Importing library
       
       ``` 
       from ProText import *        
       ```
        or
       ``` 
       from ProText import gen, low, dig,stopw, lemma, stem, spell, clean_len, WCloud, countvec, tfidf       
       ```

   + Execution of single preprocessing property on dataframe
   
      ```
       dfcleaned['tweets'] = dfcleaned['tweets'].apply(gen)   
      ```
   
   + Adding more stop words to "stopwords.words" library list
   
      ```
       stopadd = ['sample', 'much', 'thank']
      
       dfcleaned['tweets']= dfcleaned['tweets'].apply(stopw, args=(stopadd,))
                           or
       dfcleaned['tweets']= dfcleaned['tweets'].apply(stopw, args=(['sample', 'much', 'thank'],))
       ```
 
> If there are multiple lines, better convert to Dataframe

 
###  Sequential operation in a single line of command
```
       dfcleaned['tweets'] = dfcleaned['tweets'].apply(gen).apply(low).apply(low).apply(stopw).apply(lemma)
```

### Finally WordCloud
   ```
       WCloud(dfcleaned.tweets)
   ```
## Feature extraction user guide on df or list
+ For CountVectorizer
```
       cv_vect, cv_feature, cvdf = countvec(dfcleaned)
```
+ For TfidfVectorizer
```
       tfidf_vect, tfidf_feature, tfidfdf = tfidf(dfcleaned)
```
