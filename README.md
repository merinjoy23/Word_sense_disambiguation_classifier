## Word_sense_disambiguation_classifier

### Introduction :

Authors : Sai Nikhitha Madduri and Merin Joy

Date : October 31st 2018

Word sense disambiguation is a open problem in NLP and ontology, it refers to identification of in which sense a word is
used in a sentence, when the word has several meanings.

This Python program called decision-list.py implements a decision list classifier to perform word sense disambiguation by identifying features from training data. Logarithm of ratio of probabilities of both senses is used to calculate the likelihood of the learned decision rules.

Features Used: words, word indices upto 8 position on either directions

### Results :

The most frequent sense baseline accuracy of this program is 57.14%

The accuracy after adding features is 82.53%

The confusion matrix is 

col_0   phone  product
row_0
196.0     5       2
phone     59      7
product   8       45

### Instructions to run decision-list.py :

1. Run the decision-list.py program in the command prompt as follows:
$ python decision-list.py line-train.xml line-test.xml my-decision-list.txt > my-line-answers.txt
2. A text file with all decisions will be obtained in my-decision-list.txt and output text file with list of answer
instances and sense id can be found my-line-answers.txt. Also, any output file name can be specified since STDOUT function is used.

### Sample Output :

my-line-ansers.txt

'<answer instance="line-n.w8_059:8174:" senseid="phone"/>',
'<answer instance="line-n.w7_098:12684:" senseid="phone"/>',
'<answer instance="line-n.w8_106:13309:" senseid="phone"/>',
'<answer instance="line-n.w9_40:10187:" senseid="phone"/>',
'<answer instance="line-n.w9_16:217:" senseid="196.0"/>',
'<answer instance="line-n.w8_119:16927:" senseid="product"/>',
'<answer instance="line-n.w8_008:13756:" senseid="196.0"/>',
'<answer instance="line-n.w8_041:15186:" senseid="phone"/>'

### Algorithm :

* Step1: Extract the training and test datasets
* Step2: Preprocess the data and remove stopwords and punctuation
* Step3: Use conditional frequency distribution for calculating the frequencies of the learned rules from the training dataset
* Step4: Use condition probability distribution for calculating the probabilities of the frequencies
* Step5: Use logarithm of ratio of probabilities of both senses to calculate the likelihood each decision rule
* Step6: Determine the majority sense from training data
* Step7: Perform predicitons on the test dataset based on the learned decision rules
* Step8: Post the answers from the prediction to STDOUT
* Step9: Write the decision rules to a file
