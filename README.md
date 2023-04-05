
# Embedding and Prediction of Musical Notes using Skipgram Model


> 자연어 처리 모델인 Skipgram을 클래식 악곡에 적용하여 맥락있는 음들을 예측해보았습니다. numpy를 이용하여 직접 Skipgram 모델을 구현하였고, music21 모델을 이용하여 .mxl 포맷의 음악 파일을 전처리하였습니다. 자세한 분석 및 처리과정과 모델 설명은 첨부된 pdf를 참고해주시길 바랍니다. 


<hr>

### Introduction

Natural Language Processing (NLP) is a sort of Artificial Intelligence (AI) that process and analyzes the text data using Machine Learning (ML). NLP uses ML algorithm to recognize structure of text data and its meaning. NLP can help users to understand more about text data and apprehend relation between context. It is used to analyze customer’s emotion, classifying contents, medical field and etc.
<br>
Skip-gram model is one of NLP algorithm that predicting context words with regard to given words. It predicts context words with conditional probability function by what word is given as input. To analyze data with a skip-gram model, there are several conditions that data should satisfy.
<br>
First, data should be discrete rather than continuous since skip-gram model is deserve for analyzing categorical data such as text (corpus). It is not useful for continuous data because context of continuous data must have immediate predecessor and immediate successor as neighbor step, by definition of continuous function. Secondly, data should be relevant between contexts. Since skip-gram uses conditional probability function based on context, incoherent data will lead to meaningless result.
<br>
Inspired by such conditions, I came up with an idea that the melody of music can be regarded as text data and musical note data might be therefore adequate for skip-gram processing. We will deal with notes instead of words, and bars instead of sentences. Melody will used as corpus. Skip-gram algorithm will train with each piece of classical music by era (such as Baroque, Classicism, Romanticism), and predict context notes according to given input note. Moreover, based on the predictions provided by the
Skip-gram model, we will make a verse of the song that fits each age for trial. Finally, we do visualize each composer’s song and embedding matrix by t-SNE.


### Requrement

I used `python` version of `3.7` and `music21` library for preprocessing .mxl format music file.
