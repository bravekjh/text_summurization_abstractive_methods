# Arabic Text Summarization (seq2seq with bidirectional LSTM with attention)

this implementation is a continuation of the amazing work done by
- David Currie's https://github.com/Currie32/Text-Summarization-with-Amazon-Reviews seq2seq
- that was based on 
   - [Jaemin Cho's tutorial](https://github.com/j-min/tf_tutorial_plus/tree/master/RNN_seq2seq/contrib_seq2seq) 
    and 
   - https://github.com/tensorflow/models/tree/master/textsum

-------------------------------------------------


## Data :
the Arabnews data found https://webhose.io/free-datasets/arabic-news-articles/ in a json format
I have modified it to be in a csv format 

-------------------------------------------------


## Model :
Modeification of the https://github.com/theamrzaki/text_summurization_abstractive_methods/blob/master/Implementation%20A%20(seq2seq%20with%20attention%20and%20feature%20rich%20representation)/Model_1.ipynb
model 1 
but using Arabic data , and using embedded marix that was specifically trained on this corpus to get better results , I am still working on having better results isA 

Model Details :

1.   RNN :100 node
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

-------------------------------------------------

## Links
**Pickles** :
https://drive.google.com/open?id=1m5JXk5-e5dQL8-B2F2-o5etgs6_sEcMU
contains
1. sorted text / sorted summary
2. embedding matrix
3. clean text / clean summary

**Data**
https://drive.google.com/open?id=1joX6vzXoI3amiZeU37HP6VPAWrKSj1d4

**Trained Model**
https://drive.google.com/open?id=1lxR9dLWP4nc26BuPNujqAkVNOlX44l5I

**Embedded Matrix**
it has been trained over this corpus to gain the best results
https://drive.google.com/open?id=1R_ETjqlsX72XVVjvg71Qp6Zg3KzaEnmJ
https://drive.google.com/open?id=1-JeTCPSbxpjv7BUI67XC04OnDi_zIxyz
to be placed in the same folder and then to be loaded inside your code by simply 
```python
print('Loading my Model ..')
model = KeyedVectors.load("drive/Colab Notebooks/Model 2 Arab/" +"model_arabic_vec.model", mmap='r')
print('Loading Done el7 !!')
progress = ProgressBar(len(model.vocab), fmt=ProgressBar.FULL)

for word in model.wv.vocab:
      embedding = np.asarray(model[word], dtype='float32')
      embeddings_index[word] = embedding
      progress.current += 1
      progress()
progress.done()
print('\n Word embeddings:', len(embeddings_index))
print('\n') 
```

### Results/result_model_1_5_random_arab_16_3_2019_1_05am.xml
- output from Model 1_5 that have achieved el7 

> bleu="1.5980396941697776"   on 50 random article (not just validation)






-------------------------------------------------

