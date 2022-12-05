# Ex 1 rpt
This chapter presents an improved approach for estimating SoC.
Many of the same problems that are present in Chapter 3 are present here, in particular the poor experimental protocol and unclear presentation of results.
The experimental protocol seems to have changed slightly from Ch3 in that now a single datasets seems to have been designated for training, rather than rotating through all possible training sets.
The reason for this is unclear.
There is also no direct comparison to the method in Chapter 3.
The approach in this chapter appears to be based on the third method from Chapter 3, yet the system with the additional input is not compared to the original method from Chapter 3.
This needs to be rectified.
Other details within the chapter (such as the “output steps”) are not defined anywhere - the only definition of output steps is in the code in appendix H.
Other details such as efficiency, which was an important consideration in Chapter 3, have been totally omitted here.
The previous chapter also noted variation in performance between training runs, yet there is no discussion of this here.
Was this problem not observed in this case, or was it simply not considered?
As per Chapter 3, multiple trials should be run with average results reported.

# Ex 2 rpt
Modelling the dependence of the current SoC on previous SoC values is interesting, and appears to be a novel idea in the context of estimating SoC.
However, it is not clear whether this idea has been correctly implemented.
My main question is: Are measured SoC values used during both training and testing? 
Or are measured SoC values used during training, and predicted SoC values used during testing?
The textual description in Section 4.3 is confusing and vague, and the figure illustrating the idea (Fig. 4.4) does not help either: it does not differentiate measured SoC values and predicted SoC values as the same notations are used for both, and in fact the two approaches illustrated in Fig. 4.4 (a) and Fig. 4.4 (b) can both be interpreted as using the predicted SoC values during training.
As far as I can see, Fig. 4.4 does not show how the model is used during test time.

# Detailed run
## Introduction
> p73, “In this chapter, the Long short-term memory model will be developed, with a history of 8.5 minutes usage,” why 8.5 minutes? Is the the 500 timesteps from the previous chapter (at 1 Hz sampling 500 samples is 8:20)?
> > Updated with "with a history of approximately 8 minutes and 20 seconds usage (500 samples at 1Hz)"

> (pp. 73) “To address some of the limitations identified in Chapter 3”: which limitations?
> > Added "such as a training cross-accurate model and minimisation of resistance influence". I see litle point in repeating what has been said literaly two paragraphs above this chapter.

> p75, Figure 4.1 feels redundant given its similarity to Figure 3.2.
> > It is not similar and gives a clear distiguish in terms of the improvement of this method. THe similarity was kept on purpose to simplify undestanding between those chapters.

## LSTM for SoC prediction
> P76, the overview of LSTMs and Figure 4.2 is redundant, this has already been presented in the previous chapter, and you can simply refer back to the previous content
> > Added an /ifthenelse to remove that figure with content if it is a thesis, but keep it in an article.

> P77, “Besides, methods like temperature prediction a weak ahead are not limited by lacking output data.“, should be “a week ahead”, also unclear what is meant by this statement
> > TODO

> ---(pp. 77) “prediction a weak ahead” 
> > TODO

> ---(pp. 77) “no dropout technique is used in model initialisation”: dropout is not a model initialization technique
> > Corrected and refered to the previos chapter for other details.

> P77, “Figure 4.1 demonstrates how the input dataset is constructed and ordered into a 3-dimensional dataset“, 4 dimensional?
> > No, the dataset is 3-dimensional. It simply has 4 features now, rather than 3 like before. It is still [samples, timesteps, features]

> P77, “Due to the size of the windows of 500 samples, which is equivalent to 5 minutes of a discharge process”, p73 has this has 8.5 minutes?
> > 8 and quoter minutes is more writning acceptable.

> P77, “no batching mechanism has been used to reduce computational load and avoid 4-dimensional matrix management.”, unclear what is meant by this statement, do you mean that you train the model with a batch size of 1? If so, it’s unclear why you would do this.
> > batch size 1 is given in the table already. This is already slow process, adding a 4th dimension will not add any performance and only screws up the prediction. requiring further manualy adjustment to make it production usable.

> p77/8, the same questions with respect to the evaluation protocol are relevant here as per Chapter 3. It’s also unclear why only a single training scenario was considered here. In Ch3, the model was trained three times - once on each dataset, and then tested on the other two. Why is that process not followed here? A cross-fold validation would make more sense overall however.
> > Back then I had barely time to even complete this part, not to mention to run another month of computation. This time, only selected parameters were used and using the average of 5-10.

> p78/9, section 4.3, should compare to the model from Ch3 where the 3D input was used
> > TODO

## Feed-Forward prediction and Robust Auto-regresive traininig
> ---(pp. 78) “the output is expected to be within 1% miss accuracy”: “miss accuracy” means MSE? Why 1%?
> > Because when given 500 samples of SoC, prediction of 501 is a linear task, not a NN.

> P79, “Figure 4.5 contains a similar test as without autoregression. Even though the accuracy with tabled samples has decreased, its feed-forward prediction accuracy has a significant increase.“, unclear, this doesn’t make a lot of sense, and it’s hard to understand what Figure 4.5 is showing. This being “without autoregression” implies it’s a 3-dimensional input, but that does not seem to be the case. This and Figure 4.5’s caption need to be clarified.

> P80, Fig 4.4 is very poor quality
> > Figure is fine, it is a compression. However, those are PNGs, unlike all other images which are SVGs.

## Results
### Accuracy comparison
> ---(pp. 81) “Figure 4.6 outline demonstrates”

> P81, “The entire training process has been logged, and every model is saved as a separate checkpoint to determine the most efficient model in both validation and testing. Figure 4.7 demonstrates selecting the best model, marking the iteration which produced the lowest error for all three profiles.“. This is cheating. Performance on test sets cannot be used to select the model. You should: train on one dataset. Validate the model on the second, and select the best model based on performance on this dataset. Test on the third (totally unseen) dataset.

> P82, “the weight the properly applied to the correct feature over the training process“, unclear

### Optimal output step size
> P82, “4.4.2 Optimal output step size”, what are “output steps” here?

> P82, “Table 4.3: Percentage accuracy evaluation with increasing output step size”, what is this table showing? Output steps have not been defined. What is “Percentage accuracy”? Previously RMSE and MSE have been used. Is this one of these?

> P82, “The US06 and FUDS have the more aggressive current usage, leading to trendier voltage readings.“, what are “trendier voltage readings”?

## Conclusion 
> P83, Figure 4.7, what is the x-axis showing? The label text is iterations/epochs, is this iterations divided by epochs?

> P84, “The experiment has proven that State of Charge prediction models tends to put significant weight into the Voltage to describe the charging process during the model training process.”, what experiment? Chapter 3?

> P84, “Adding the charge as a feature has proven that the history of the charge had a higher weight on a system than sensory data.”, as per Chapter 3, these weights are discussed but never shown.

> ---(pp. 94) “forward teaching”: provide a citation for this name. If I understand correctly, this refers to what is known as teacher forcing in deep learning (e.g., see [Goodfellow et al., 2016]).