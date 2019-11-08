# TFIDF using Map Reduce (Hadoop) 

#### 1. Data Extraction and Data Loading using Pig and Hive


#### 2. TF-IDF Calculation using Map Reduce:
Implementation of TFIDF in Hadoop using Python as three phases


#### 2.1 Phase One:
Mapper  : ((word, User_ID), 1)\
Reducer : ((word, User_ID), word_count_in_doc)


#### 2.2 Phase Two:
Mapper  : (User_ID, (word, word_count_in_doc))\
Reducer : ((word, User_ID), (word_count_in_doc, words_in_doc))


#### 2.3 Phase Three:
Mapper  : (word, (User_ID, word_count_in_doc, words_in_doc, 1))\
Reducer : ((word, User_ID), tf-idf)


#### - Hadoop commands for TF-IDF Calculation:
hadoop jar /usr/lib/hadoop-mapreduce/hadoop-streaming.jar -file "Mapper Path" MapperPhaseOne.py  -mapper "python MapperPhaseOne.py"  -file "Reducer Path" -reducer  "python ReducerPhaseOne.py" -input "Program Input path and file_name" -output  "Program Output path and file_name"
