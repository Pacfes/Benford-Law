# Authors

+ Pedro Fernandes - Department of Computer Engineering; Limerick Institute of Technology; Limerick, Ireland; Pedro.Fernandes@lit.ie
; Mathematics Department; Polytechnic Institute of Leiria; Leiria, Portugal; pedro.a.fernandes@ipleiria.pt
                  

+ Mário Antunes - Computer Science and Communication Research Centre (CIIC), School of Technology and Management, Polytechnic of Leiria; Leiria; Portugal;   mario.antunes@ipleiria.pt
INESC TEC, CRACS; Porto; Portugal

# Benford's law-based method

Several scripts are presented, some built-in Python (Conversion, Extract-features) and others in Matlab (Extract first digits, Tables CVM, Spearman and Pearson). The procedure is started by extracting the first digits from a database containing manipulated and authentic images (Extract-features). 
Subsequently, the obtained values are stored in a database and converted from .py format to .xls format (Conversion). The first digit is extracted from this database, and the hypothesis tests (Pearson, Spearman and Cramer Von Mises) are applied. 
This procedure will allow the classifications. This entire classification procedure can be carried out by calculating the P-Value obtained from the correlation between the empirical frequency of occurrence of the digits from Benford's law and the relative frequencies of the digits extracted from the set of images.

# Dataset containing manipulated and authentic images

![Dataset](Dataset.jpg)

The database used for the tests is available [here]


# General architecture of the method based on Benford's law

![General architecture](Pre-processing.jpg)

The pre-processing consists in extracting a set of n features from the images by applying the DFT (Discrete Fourier Transform) method. For this, a Python script was built, where besides the standard libraries NumPy, pickle, the libraries OpenCV were used to process the image. A script was built for the radial profiling function, whose main function is to create a circular boundary in the image, extracting only the features within the circular zone. The extracted data is stored in a dataset, where through the development of a script built in MatLab, the first digit of all the obtained values was extracted and subsequently stored in a digit matrix.

The data relating to the extraction of the first digit from each image is appropriately stored into a feature vector, and each is labelled, that is, if the image is original, it is assigned the label 1;  otherwise, the image is manipulated and is assigned the labelled with 0.

At the end of pre-processing, an adequately labelled dataset is available to apply a set of hypothesis tests based on Pearson, Spearman and Cramer-Von Mises statistical models. 

The processing phase consists of two steps. The first step consists in counting the first digits from the values obtained in the pre-processing phase for each image. In contrast, the second step calculates the absolute frequency of each digit, having the whole database as a reference. Then, the relative frequency of the values obtained in the two previous steps is calculated, consisting of the quotient between the absolute frequency of each digit and the sum of the total number of digits of each image under study, allowing the subsequent comparison with Benford's law. Finally, the values obtained by the relative frequency calculation are duly stored in a data set for further investigation, determined by two significant moments: hypothesis tests and graphically.






