# Arabic Text Summarization (seq2seq with bidirectional LSTM with attention)

this implementation is a continuation of the amazing work done by
- David Currie's https://github.com/Currie32/Text-Summarization-with-Amazon-Reviews seq2seq
- that was based on 
   - [Jaemin Cho's tutorial](https://github.com/j-min/tf_tutorial_plus/tree/master/RNN_seq2seq/contrib_seq2seq) 
    and 
   - https://github.com/tensorflow/models/tree/master/textsum

## Data :
the Arabnews data found https://webhose.io/free-datasets/arabic-news-articles/ in a json format
I have modified it to be in a csv format 


## Model :
Modeification of the https://github.com/theamrzaki/text_summurization_abstractive_methods/blob/master/Implementation%20A%20(seq2seq%20with%20attention%20and%20feature%20rich%20representation)/Model_1.ipynb
model 1 
but using Arabic data , and using embedded marix that was specifically trained on this corpus to get better results , I am still working on having better results isA 

Model Details :

1.   RNN :256 node
2.   2 Layers
3.  150 length of Embedding Matrix using the word2vector that i have generted for training
4.   Original function of sorting of data before training of David Currie's
5.   training 1 session as i remember (loss of about 2)
6.   training on 39708 article (after the function of sorting )
7.   no changes to the orignal model
8.  coverage of embedding was about 

> Total number of unique words: 544525
> Number of words we will use: 309353
> Percent of words we will use: 56.81%


### Results/result_model_1_5_random_arab_16_3_2019_1_05am.xml
- output from Model 1_5 that have achieved el7 

> bleu="1.5980396941697776"   on 50 random article (not just validation)






-------------------------------------------------

