# Journal Article - Autoregression

General information that is necessary for deployment and compilation.

## Structure content

Overview of each paragraph section by section with a brief description of each content and comments from examiners.

> (1, 2 .. ) BlockQuote is used to indicate exameners comment. Number refers to one of them
>
>> This is my respone or soulution I provided
>>
>>> 3rd or every odd line will be refered by supervisors and co-authors.
>>>
>>

```
Marking of the psudocode or reference to whatever implementation it is refeered
```

## Mutually correlating/contradicting feedback

> (1) in the abstract please avoid using the reference link to a previous publication ([...] upon earlier published findings, assessing several models ability to estimate SoC using a history window of sensory data (Sadykov et al [23]), this work proposes [...]), it would be better rephrasing or simply erasing the reference.
>
> (1) usually in the abstract is preferable not to use acronyms.
>
> (2) The abbreviation was disordered. Some abbreviation is explained several times. It is presented only for the first time when it appeared, then the abbreviation should be used instead of the full name. If the abbreviation had been explained in the abstract. The author can use it directly in the text of the paper.
>
>> As requested, the reference in the abstract (Page 1, Line 18) has been removed.
>>
>> Following acronyms were changed to the full or equivalent meanings, without affecting the context: (Page 1), (Line 18) SoC -> charge, (Line 19) RNN -> neural network, (Line 23) RNN -> (removed completely).
>>
>> Since the declaration of abreviations in Abstract for the reuse purposes is permitted, any repated definitions of SoC and RNN were removed from introduction. (Page 1, Col 1 Lines 47, Col 2 Line 46)
>>

> (3) In introduction, could a table be added to show more clearly the general review of the application of machine learning methods to SOC estimation.
>
> (3) The author's contribution and the specific problem being addressed should be listed in an organized manner at the end of the introduction.
>
> (4) The contributions in Introduction section are also very generic. Please provide concrete quantitative findings to highlight how the paper addresses the current problem.
>
>> To avoid the reuse of the same table from previos article and save space in introduction, that table has not been included, instead a single sentance on (Page 1, Col 2 Lines 56-57) was introduced to cover that, in addition to the reference to that work (Page 1, Col 2 Line 58).
>>
>> Following paragraphs has been pulled from early versions of the Introduction which replaced Page 2 Col 1 Lines 33-48: *However, the risk could be reduced by using initial SoC from other means, like 3-feature based models discussed in previous work [23], or by employing the charge feature to those models utilising an autoregressive technique [17] to avoid the propagation of prediction error.*
>> Additionally, removing Page 2 Col 2 Lines 3-9 and replacing 2nd last paragraph with following paragraph has been introduced: *This paper will carry on the previous findings to overcome identified issues in the estimation of full-cycle battery utilisation and propose a new method, which has not been researched deeply enough. A novel method for implementing a SoC estimation training loop will be presented based on the autoregressive technique, which uses a 4-feature input (current, voltage, temperature, and SoC), with a history of 8 minutes and 20 seconds usage (500 samples at 1Hz), and increases SoC prediction accuracy, while avoiding the accumulation of prediction error that might otherwise make a feed-forward based model infeasible. That way, the model will be forced to consider the miss accuracy of its State of Charge prediction before loss calculation. \n The rest of this paper is organised as follows ...*
>>

> (3) The quality of Figure (5) and Figure (7) is poor, which needs to be improved.
>
> (4) The author should increase the resolution of some of the images to achieve a uniform resolution throughout the document.
>
> (4) The author should carefully review the manuscript, for example, Figure 5 is not displayed in the manuscript.
>
> (4) Diagrams should be added to illustrate the workflow of the proposed methods for better understanding.
>
>> Figure 5 was increased in scale to 1.05 with cropped white space around graphs. Also, the font of the text has been changed to match the rest of the plots. Before, Figure 7 was scaled down to 0.85 to avoid extra page 13. The scale has been restored to 1, and titles were removed. The remaining vector graphic have fit itself to match the context resolution.
>>
>> Majority images, apart from Figure 5 and 7 are vector graphics (SVGs) generated from the code. The resolution should not be affected after document compilation and may happen to be affected via Zoom tool of PDF readers.
>>
>> To illustrate the workflow of the proposed method, the Figure 7 has been created as the best and simplest illustration we were able to come up with to a complex code-written procedure.
>>

> (1) Literature review can be improved by providing more research for models that are used for calculating the SoC of the battery (CNN with/or GRU, LSTM, BiLSTM, BiGRU) using different or CALCE dataset.
>
> (4) The introduction mentions GRU; therefore, why was LSTM chosen as the research object instead of the GRU network?

>> (There is a short refernece mentioning that, better not to repeat previous work). **I have to figure out how to refuse that request, especially since he mentioned "can be improved". With 2.2 removal, the text made a nice fit with figures.**
>>
>
>> **As an option, adding extra mentions of e.x BiLSTM on Page 1 Col 2 as per references which they are defined from could tick that box. However, another examiners noticed that mentioning GRU brought only confussion for those who unfamiliar with the cotext and results of the previous work.**
>>
>> (Page 2, Col 1 Lines 7-8) clearly state that the LSTM with Attention Layer showed the best results to given problem, therefore the GRU mentioning was only added for introduction purposses and that it has been considered for usage. However, to avoid the confusion and since it was used in the previous article, the line mentioning GRU methods can be removed if requested (Page 1, Col 2 Line 57)
>>

## Examiner 1 feedback

Although the paper is well written amd the genearl idea is clear, some aspects should be improved, expecially clarifying the actual implementation in real time application of the proposed methodology.

> In real-time applications how does the information of the true initial SoC, which is used to make the first estimation, will be known (as an error in those values might lead to serious divergences in the model estimations)?
>
>> To address this point, a clarification has be added to text: instead of "... with other NN methods" on Page 3 Col 1 Lines 42-45 the " ... *with previously determined best LSTM with Attention model*." has been used instead.
>>

> Paragraph 2.2 could be reduced and summarized as LSTM is well-known in literature.
>
>> The content starting from Page 3 Col 2 Line 14 - 34 has been removed, as it was correctly noted. As the results, all the remaining content were shifted to Page 3 (which made a perfect fit for the article), with Page 4 dedicated to Figure 4, followed by exact explanation.
>>

> There are plenty of images that were also used in a previous paper (that is [23]) which are different in the real implementation, as it is also mentioned by the authors. The correct figures for the real implementation should be provided. Moreover, in Figure 5 there is a possible mistake in the output values SoC_(s), SoC_(s+1), SoC_(2s+1),...(Should the SoC_(s) be SoC_(1)? ). Please check and, if it is not wrong, provide further explanation of the step in which the SoC values are calculated.
>
>> The real implementation is potentially referered to the Figure 5 description, which referes to "visualisation purposes". Othervise, Figure 2, which would impact the perception of the results if removed.
>> By the initial idea, s was meant to equal 1, since this is one sample step the data take, making SoC_(s) to be SoC_(1). However, since it brought more confussion, the Figure has been updated as recommended and further clarifications were made: Page 4 description - "... *zero, excluding possible initial data discrepancies*." Page 5 Col 1 Lines 30-33 - "*Here, in Figure 4, a time-series training set of equally spaced data points is broken up into "windows" of a set width (5 samples in this case), with a difference by one sample from the previous one by s-step. A window is defined starting at each data point so that each window overlaps with the next windows, shifted by s number of samples.*" Page 5 Col 1 Line 43 "...*process, with only 1 sample shift s between each other, no batching*..."
>>
>> To avoid further confusion with Section 2.3, the intext s step size in Page 5 Col 1 Line 22 has been renamed to AR with equivalent change on Table 1.
>>

> Figure 1 could be misleading: apparently data employed for validation are included in the training set. If not, please correct the image.
>
>> Indeed they are included, only to verify the state of the model to ensure no overfitting, mentioned in Page 7 Col 2 Line 48. That is why validation was done on the testing data, like it is stated on the Page 2, Col 2 Lines 49-51. An extra clarification was introduced to Page 2, Col 2 Lines 58: "... *training, validation for any divergence in the fitting process and*..." Another clarification has been used already on Page 3 Col 1 Lines 60-61 and later in results Page 7 Col 2 Lines 35-38.
>>

> as regards Table 4, in the description text below (lines 48-49), please better clarify that employed data in the training are not the same used for the testing (even if they belong to the same cycle profile).
>
>> No, the Trained on DST and Tested on DST or with other models simply reports the training error, which has been done on the same dataset of the same cycle profile. Training values of plots Figure 9 (a,d,g)). The appropriate sentence has been added on Page 8 Col 2 Line 28: "*Matching profiles in the Trained and Tested row and column report the training error, verified separately after concluding the fitting process along with other profiles.*".
>>

> in some cases acronyms are defined (as SoC for the State of Charge) but they are not consistently used. Please check along the text.
>
>> Following State of charge definitions were replaced:
>> Abstract: State of charge -> charge percentage
>> Introduction (Page 1, Col 1 Line 37): State of charge -> charge percentage
>> Section 2.2 (Page 5, Col 1 Lines 49-50): State of Charge -> SoC, SoC -> a single SoC value
>> (Page 5, Col 2 Line 19) State of Charge -> SoC
>> Section 2.3 (Page 6, Col 1 Line 27) State of Charge -> charge value
>> (Page 6, Col 1 Line 46, Col 1 Line 58) State of Charge -> SoC
>> Conclusion (Page 9, Col 2 Line 52): State of Charge -> charge peercentage
>> (Page 11, Col 1 Line 48) State of Charge -> SoC
>>

> in the Bibliography, reference 22 is exceeding the column format. Please fit references to the column width.
>
>> A new line symbol has been added in the mid of the reference link in the .bbl file to correct this.
>>

## Examiner 2 feedback

The novelty of the paper is not clear. The structure and content of the paper is not valued to be documented now. The format of the paper cannot warrant its publication in this journal. Some suggestions and advices are as follows:

> Improve the overall consistency and "look-and-feel" of the figures. They should have the same fonts, font size, axes formatting, etc., as is appropriate for a high-quality journal. Make sure that fonts used in figures (labels, annotations, callouts, ...) are similar in size to the fonts used in the main text and no smaller than the font size of the figure captions. Use high-resolution graphics. For example, figure 5 and figure 3 were not clear enough for the reader.
>
>> Figure 5 white borders were removed and increased in scale to 1.0, and Figure 3 removed from the context completely.
>>
>> The original figure fonts were modified with STIX, as per LaTeX template.
>>
>> Figure 1,2,6,7 - removed title and white space around borders to make a better fit. Captions updated accordingly.
>>
>> Figure 9 - removed titles to avoid repeated or overwealmed information is subfigures.
>>
>> Figure 10 - titles removed. Captions and description updated to preserve information.
>>

> The paper title was confused. No battery appeared in the title.
>
>> If editor would permit of usage chemical formulas, we would liek to propose followign title to address that point: "Feed-Forward State of Charge Estimation of LiFePO_4 Batteries Using Time-Series Machine Learning Prediction With Autoregressive Models", as it perfecrly fits into two lines of the title space.
>>

> The first reference number was 12. It was strange. The references should be indexed by sequence.
>
>> The supplied style of bibliography (*cas-model2-names)* does not emply sorting. Switching to (*unsrtnat)* for now, which later can be changed by editors if needed, has resolved that issue.
>>

> The writing of the paper was poor. The authors should improve it before it was submitted to an academic journal.
>
>> The similar state of the paper already went through one prof reader during the MPhil submission, as well as 9 edits with supervisor. If it is required, it can be sent to another one, from the journal, similar to first publication.
>>

## Examiner 3 feedback

The paper contains sufficient experiments and proper use of methodology.

> Should Equation (1) be RMS Error instead of ABS Error?
>
>> The error calculation on the graphs has been done with Absolute error. To avoid similarity with RMS, and avoid the reuse from previos work, the square and sqrt has been replaced with module symbol.
>>

> Table 1 demonstrates model structure and parameters, and obviously this is just a single-layer LSTM-RNN. Whether some enhancements of networks structure can further improve the effectiveness of this approach needs to be discussed.
>
>> No other uses of that process has been located in publications, therefore it was kept simple as a possible introduction for further improvements. Following statement has been added in (Page 5, Col 2 Line 28): "... set [23]. Only a single layer RNN will be utilised throughout the work due to the primary focus on the Autoregression method that requires proper testing before further improvements. Therefore, an effective combination of layers and neurons will be outside of the scope and will only be based on the results discovered early. The results section was adapted to the new ... "
>> Additional sentence to conclision has been added to refer this moment (Page 11, Col 1 Line 40): "The single-layer implementation implied further improvement of the method with enhanced network structure via multilayers or a higher number of neurons, which can be considered a future work. Besides, while the method has proven ... "
>>

> A discussion of the advantages of the proposed approach needs to be added to section III or elsewhere.
>
>> Currently, Section 2, 2nd last paragraph and Section 3 last paragraph, provide sufficient information to support the advantages of the proposed mothods, in addition to updated introduction and conclussion. No new information, that hasn't been mentioned already, can be provided to support the point without overwealming the reader with more repeated information.
>>

## Examiner 4 feedback

> The author should check whether the formula expressions are correct and the variables in the formulas should be explained.
>
>> The formula expressions are correct and were determined from the first principal, all variables are explicitly defined at the point of their definion. The LSTM cell discussion has been removed that potentially resolved that issue.
>>

> Figures and tables should be placed as close as possible to their corresponding textual explanations.
>
>> Text vise, Figures and Tables are located at the end of every paragraph, where they are defined for the first time, or right after so that the order of numbering is preserved along with context. The positioning has been done with LaTeX compiler to create the best possible fit.
>> With Figure 3 removal from the text and corresponding content, the figure placement has been brought closely to their intext definitions, especially on Pages 6-9.
>>

> Additional experiments should be conducted to validate the model's performance, such as estimating SOC results at different temperatures.
>
>> Such experiment has been concluded in the results section, where each plot on Figure 9 (c,f,i) demonstrates 2 cycles for each scheduler. The Table 4 accuracies are calculated based on the entire dataset testing. Page 8 Col 1 Line 60 has been updated with "... model across the entire dataset for every temperature range are ..."
>> It was a necessary trade off in order not to scale to same page numbers as the first article and still provide enough information for readers to follow the process.
>>

> The performance of the proposed method should be compared with other methods.
>
>> Table 4, best two picks from previos paper,which already compared other methods. Placing them here would only take space, worse readibility with unncecessary information, forcing reader to compare with whatever already had to be compared before.
>>
