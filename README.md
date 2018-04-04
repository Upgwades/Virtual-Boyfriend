# Virtual-Boyfriend

A fork of a repo altered to work in Python 2.7, a tensorflow powered chatbot so I don't have to talk to my girlfriend when I don't want to.

Joking aside this project is an attempt to use Google's famous [seq2seq paper](https://arxiv.org/abs/1703.03906) to build a chatbot with the linguistic signature of the person whose conversation data was used to train it.

The potential applications of such a chatbot would be far reaching. The authors of paper would be able to answer nuanced questions with detailed responses without having to take any time or effort to do so as one example. 

## Running It

Much of the details for getting this repo running are detailed in the repo listed below and as such those will not be mentioned.

The changes this project makes aside from miniscule changes to be Python 2.7 compatible include overhauling the data preprocessing script to work with data pulled from a free widely available text message backup [app](https://play.google.com/store/apps/details?id=com.riteshsahu.SMSBackupRestore&hl=en).

### Inputs

A "pre" preprocessed xml file containing text message data. The default output of the app contains a good deal of superfluous information and still needs a small amount of cleanup accomplished by any capable text editor like notepad++.

**Note** this extra step can be taken care of easily by reworking the createDataset.py script. 

After that its a simple matter of running the word2vec.py script to quantify the text data and subsequently running the seq2seq.py script to train the model on the provided text.

### Outputs

The output during the author's testing was usually unremarkable. After several hours the program finally stopped returning spaces or simply "lol". Unfortunately training was halted at this point due to time constraints. If CUDA had been utilized or more time alotted than meaningful responses would likely have been generated.

## Possible Changes

* Use of the CUDA version of TensorFlow to speed up training and produce meaningful responses.
* Use of a substantially larger corpus of data.
* An increase in the quality of data; the model is not able to understand some of the nuances of personal texting style versus the actual response to a message. For example the training data used by the author would sometimes contain multiple responses to (out of order too) to questions asked as input. The model cannot understand this habit and will unintentionally learn to respond to incorrect pairs of input/output. 

## Authors

* **Will Irwin** - *Everything* - [Upgwades](https://github.com/Upgwades)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Heavily inspired by this [repo](https://github.com/adeshpande3/Facebook-Messenger-Bot) by [Adit Deshpande](https://github.com/adeshpande3)
* Google's seq2seq [repo](https://github.com/google/seq2seq)
* Stackoverflow was very helpful
