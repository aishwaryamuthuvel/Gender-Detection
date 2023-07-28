# Gender-Detection

This work proposes the development of machine learning models to recognize the gender of an individual by analyzing their recorded speech signal. The vocal folds are an important aspect of the human voice. The length of the vocal cord is gender-dependent. Males tend to have longer vocal folds than females and in turn, males have a heavier voice with more intensity when compared to females. Based on this idea, a gender detection system is proposed in this paper.

## Dataset

The speech database which was used for our experiment was recorded manually with the use of the Alesis io4 USB Recording Interface. The iO4 is a compact audio-recording interface for home, project and portable studio recording setups. By using this device and [Praat](https://www.fon.hum.uva.nl/praat/), a speech analysis software, we recorded 24 recordings from 8 volunteers, 3 recordings per volunteer. Each individual was given one common sentence and 2 sentences of their choice and all the recordings averaged up to 3.5 seconds of duration. The participants were asked to sign a consent form to let us use their voices for this work and complete information on the research process was made clear to them before proceeding with the recordings. In addition to this, voice recordings from an open dataset were also used for model training and evaluation. As a whole, we had a total of 100 recordings, 50 voice recordings each for males and females. We used 60 of these for training, and 20 each for validation and testing.

## Method

### MFCC 

