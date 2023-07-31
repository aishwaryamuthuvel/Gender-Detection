# Gender-Detection

This work proposes the development of machine learning models to recognize the gender of an individual by analyzing their recorded speech signal. The vocal folds are an important aspect of the human voice. The length of the vocal cord is gender-dependent. Males tend to have longer vocal folds than females and in turn, males have a heavier voice with more intensity when compared to females. Based on this idea, a gender detection system is proposed in this paper.

A detailed report on the proposed method could be found [here](https://github.com/aishwaryamuthuvel/Gender-Detection/blob/main/Gender%20Detection%20through%20Speech%20Processing.pdf).

## Dataset

The speech database which was used for our experiment was recorded manually with the use of the Alesis io4 USB Recording Interface. The iO4 is a compact audio-recording interface for home, project and portable studio recording setups. By using this device and [Praat](https://www.fon.hum.uva.nl/praat/), a speech analysis software, we recorded 24 recordings from 8 volunteers, 3 recordings per volunteer. Each individual was given one common sentence and 2 sentences of their choice and all the recordings averaged up to 3.5 seconds of duration. The participants were asked to sign a consent form to let us use their voices for this work and complete information on the research process was made clear to them before proceeding with the recordings. In addition to this, voice recordings from an open dataset were also used for model training and evaluation. As a whole, we had a total of 100 recordings, 50 voice recordings each for males and females. We used 60 of these for training, and from the remaining 20 each for validation and testing.

## Method

### Feature Extraction
#### Mel-frequency cepstral coefficients

The sound that comes out of humans differs with respect to the shape of the vocal tract, this difference can be determined from the power spectrum of the voice recordings. Mel-frequency cepstral coefficients (MFCC) can be used to pick out the spectral features that will help determine the shape of the vocal tract. The Praat software was used to compute the MFCC. 12 coefficients were calculated for each time window of 25s and the mean of these coefficients for each voice recording was used as features for the classifier.

### Classifier Training

For our problem statement, we have considered a neural network with 12 input neurons to take the 12 MFCC coefficients as input. This is passed through a hidden layer to obtain the output that could be thresholded to classify the speech signal as either belonging to a male or a female. Neural networks with a varying number of neurons, from 1 to 10 in the hidden layer were trained and evaluated on the validation data. The figure below shows a plot of the error rate versus the size of the hidden layer. We obtained the minimum error rate when the size of the hidden layer was 8 and so this network was finalized and its performance on the test data is shown in the table. 

<p align="center">
<img src="https://github.com/aishwaryamuthuvel/Gender-Detection/blob/main/NN_error.png" width=70% height=70% />
</p>

## Conclusion

An accuracy of 95% was achieved on the test data when it comes to recognizing the gender to which a given voice belongs. Although this conclusion drawn from the results could not be generalized mainly due to the restricted dataset that we worked with. A wider dataset with voices collected from more number of individuals could have helped make the dataset more diverse and the problem solution more generalizable. In the future, we could explore modelling solutions with lesser computation complexity. For example, using features that are simpler than MFCC to model a solution could be explored. Adding additional criteria like detecting the age group of the individual along with the gender could add complexity to the problem statement but at the same time will also require adequate data that are rightly labelled. 




