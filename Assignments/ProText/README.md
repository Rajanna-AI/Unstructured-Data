# ProText makes your Text Preprocessing tasks easy for NLP applications

A Helper pip package for text prepocessing. 

This pip package helps you execute text cleaning like 

   + General cleaning (Removal of URL, @username, addtional whitespaces, Hashtags, punctuations..etc)
   + Stopword removal, 
   + Stemming, 
   + lemmatiing, 
   + Removal of single or two character word, 
   + Converting to lower case,
   + Removal of digits
   + Spell correction
   + Creating of Wordcloud & line graph

All of these can be executed in a single line of command sequentially in any prefered order or can be executed in multiline.

> Package can be executed on both panda DataFrames and single line of text

This tool can be really helpful and No one neither needs to rememebr various syntax associated with processing nor packages.

This packages reuses funstions from nltk, Textblob and wordcloud for the above operations.

### Assumptions:
   - Assuming python is installed on your system.
   - nltk, Textblob and wordcloud installed on your system

Install `ProText` on your system using :

   ``` 
    pip install ProText 
   ```
----
## Text Preprocessing user guide on --df-- or --text--
----
   + Importing library
       
       ``` 
       from ProText import *        
       ```
        or
       ``` 
       from ProText import gen, low, dig,stopw, lemma, stem, spell, clean_len, WCloud       
       ```

   + Execution of single preprocessing property on dataframe
   
      ```
       dfcleaned['tweets'] = dfcleaned['tweets'].apply(gen)   
      ```
   
   + Execution of single preprocessing property on text
   
      ```
       tweets = "Second RCMP NL employee tests positive for Covid-19 - https://t.co/ihQIZWJEWY"
       tweets = tweets.gen()   
       ```
   
>If there are multiple lines, better convert to Dataframe
---   
### Sequential operation in a single line of command
----  
      ```
       dfcleaned['tweets'] = dfcleaned['tweets'].apply(gen).apply(low).apply(low).apply(stopw).apply.lemma
      ```
