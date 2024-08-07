# AI-in-Time-Series
Classification of Control VS Damaged Pre-Frontal Cortex during a working Memory Task.
# project description 
In this project we used different classification methods to classify two groups of paitents based on their brain pre-fronatal cortex signals during a working memory task.
# Dataset
our dataset includes EEG signals for 20 patients, 10 of which being control cases and 10 damaged.
# Data Pre-Processing
Training our model on such a scarce data is not likely to lead us to a good classification Performance as we need more data in order to let the model learn the pattern for each codition. Thus, use each trial per patient as a separate data, and given that for each patient we have 256 trials, this metodology provides us with enough data ensuring sufficient training. 
Each trial has got 64 channels representing the number of electrodes recording the EEG signal. Our feature dimension space seems to be very Large, so we need a dimension reduction strategy- which is PCA- to map the feature space to a space where data has the maximum variance.
One other pre-processing step is to map features to fourier space where we can remove the frequencies that are noise and consider the power of this frequencies as our features. However, Fourier Transformation assumes the signal to be stationary while EEG signals are not stationary and thus we use another transformation which is wavelet transform- this approach captures the varying frequencies for each time interval. Then the coefficients of such transformation can be used as our feature space.
# Classification Models
Preparing our data, we implemented random Forest, and SVM and were able to get 70% accuracy on our classification task with random Forest.
# Data visualisation and further analysis
along our classification task, we tried to get an idea of the difference betweeen the damaged and the control cases. 
As the first step we compare the average control cases with damaged cases. according to these plots damaged condition can be attributed to a more fluctuating pattern.
![image](https://github.com/user-attachments/assets/c6d49a21-0011-4014-a584-c1f4e472f233)
Implementing fourier transform, we get the following plots:
![image](https://github.com/user-attachments/assets/abfc36fd-47e4-4d60-a8b1-fdc74b373f4a)
It confirms that the damaged condition is associated with more fluctuations and wider range of frequencies.
Another informative concept is the occurence of events. we can pot events by setting a threshold beyond which we consider a puls to be an event. Below is the plot of events for both conditions:
![image](https://github.com/user-attachments/assets/c774946c-32a1-4427-9b48-c0af7657a9ae)
![image](https://github.com/user-attachments/assets/81876218-0bd7-4637-894a-726bc0dd23b4)
which is again in compliance with our initial interpretation based on which a damaged pre-frontal cortex undergoes more fluctuations/events.

