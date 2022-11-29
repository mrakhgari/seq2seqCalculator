# seq2seqCalculator
Seq2seq stands for “sequence to sequence”. This kind of model is used, like that name says, to map one type of sequence to another type of sequence. For example this is used in translation where the sequences consist of texts that need to be translated from one language to another. 

## Model
The model consists just of a number of RNN layers, with LSTM cells. After the first layer we use a RepeatVector layer. After the other RNN layers we use a Dropout layer. After the RNN layers we have a TimeDistributed layer.


### Encoder-Decoder architecture

Encoder-Decoder is a successful architecture for Seq2Seq tasks with different lengths of input and output sequences. The main idea is to use two recurrent neural networks, where the first neural network encodes the input sequence into a real-valued vector and then the second neural network decodes this vector into the output sequence.



## Data

One benefit of this task is that you don't need to download any data — you can generate it on your own! We will use two operators (addition and subtraction) and work with positive integer numbers in some range. Here are examples of correct inputs and outputs (you can change operators to "+-*/" and also can use negative numbers): 
```
Input: '1+2'
Output: '3'

Input: '0-99'
Output: '-99'
```

## Run code
### Install requirements
``` bash
pip3 install -r requirements.txt
```

### Change variables
In the setup variables cell, you can change the variables you need to run. Below we describe them:
- ```allowed_operators```: the operators that we can use in an equation, by default value is "+-". you can add "*" and "/" to it.
- ```x_max_length: ``` for training a model, we need to pad all data to the same size. x_max_length is the maximum of an equation. for example for 3 digit number the value is 7: 3(length of the first operand) +1 (operator)+3( length of the second operand).
- ```y_max_length:``` we also need to pad the solutions to the same size. 

## Some Result
In the below section, you can see a test for 20 test cases, the model training variables are: ```epochs:150```, ```allowed_operators="+"```, and the maximum of numbers in each operand is 100.

```
  94+49 Expected= 143, Predicted= 143
   62+3 Expected=  65, Predicted=  65
  80+39 Expected= 119, Predicted= 118
  26+83 Expected= 109, Predicted= 109
  77+79 Expected= 156, Predicted= 156
  88+51 Expected= 139, Predicted= 139
  61+33 Expected=  94, Predicted=  94
  69+48 Expected= 117, Predicted= 117
  35+78 Expected= 113, Predicted= 113
  76+73 Expected= 149, Predicted= 149
  55+35 Expected=  90, Predicted=  90
  56+65 Expected= 121, Predicted= 121
  76+11 Expected=  87, Predicted=  87
   57+1 Expected=  58, Predicted=  58
  54+89 Expected= 143, Predicted= 143
   21+5 Expected=  26, Predicted=  27
  60+49 Expected= 109, Predicted= 108
   99+0 Expected=  99, Predicted=  98
  99+79 Expected= 178, Predicted= 178
   50+6 Expected=  56, Predicted=  56
```
