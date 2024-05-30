# Journal Article

This is general information of the article, necessary for deployment and compilation.

## Structure content

Overview of each paragraph section by section with a brief description of each content and comments from examenors.

> (1, 2 .. ) BlockQuote is used to indicate exameners comment. Number refers to one of them
>
>> This is my respone or soulution I provided
>>
>>> 3rd or every odd line will be refered by supervisor.
>>>
>>

```
Marking of the psudocode or reference to whatever implementation it is refeered
```

## Mutual corelating feedback

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
> (4) The introduction mentions GRU; therefore, why was LSTM chosen as the research object instead of the GRU network?
>
>> To avoid the reuse of the same table from previos article and save space in introduction, that table has not been included, instead a single sentance on (Page 1, Col 2 Lines 56-57) was introduced to cover that, in addition to the reference to that work (Page 1, Col 2 Line 58)
>>
>> **Page 2 Col 1 Lines 20-51 Need to consult with that. Current arrangement requires no extra sentences to be added, therefore 2nd last paragraph of introduction has to be rethinking. Following paragraphs has been pulled from early versions of the Introduction which can replace Page 2 Col 1 Lines 33-48:** However, the risk could be reduced by using initial SoC from other means, like 3-feature based models discussed in previous work [23], or by employing the charge feature to those models utilising an autoregressive technique [17] to avoid the propagation of prediction error.
>> **Removing Page 2 Col 2 Lines 3-9 and replacing 2nd last paragraph with:** This paper will carry on the previous findings to overcome identified issues in the estimation of full-cycle battery utilisation and propose a new method, which has not been researched deeply enough. A novel method for implementing a SoC estimation training loop will be presented based on the autoregressive technique, which uses a 4-feature input (current, voltage, temperature, and SoC), with a history of 8 minutes and 20 seconds usage (500 samples at 1Hz), and increases SoC prediction accuracy, while avoiding the accumulation of prediction error that might otherwise make a feed-forward based model infeasible. That way, the model will be forced to consider the miss accuracy of its State of Charge prediction before loss calculation. \n The rest of this paper is organised as follows ...
>>
>>
>> (Page 2, Col 1 Lines 7-8) clearly state that the LSTM with Attention Layer showed the best results to given problem, therefore the GRU mentioning was only added for introduction purposses and that it has been considered for usage. However, to avoid the confusion and since it was used in the previous article, the line mentioning GRU methods can be removed if requested (Page 1, Col 2 Line 57)
>>
>

> (3) The quality of Figure (5) and Figure (7) is poor, which needs to be improved.
>
> (4) The author should increase the resolution of some of the images to achieve a uniform resolution throughout the document.
>
> (4) The author should carefully review the manuscript, for example, Figure 5 is not displayed in the manuscript.
>
> (4) Diagrams should be added to illustrate the workflow of the proposed methods for better understanding.
>
>> Figure 5 increased in scale to 1.05 with cropped white space around graphs. **Similar figure in previous work had no issues with editors**. Figure 7 was scaled down to 0.85 to avoid page 13. The scale has been restored to 1, which brough it back on the same page with Figure 6.
>>
>> Majority images, apart from Figure 5 and 7 are vector graphics (SVGs) generated from the code. The resolution should not ne affected after document compilation.
>>
>> **Figure 5 is present, just as a big and rotated  ... . Well it require some work for sure now.**
>>
>> Figure 7 is the best and simplest ilustration we were able to come up with to a complex code-written procedure.
>>

## Examiner 1 feedback

Although the paper is well written amd the genearl idea is clear, some aspects should be improved, expecially clarifying the actual implementation in real time application of the proposed methodology.

> In real-time applications how does the information of the true initial SoC, which is used to make the first estimation, will be known (as an error in those values might lead to serious divergences in the model estimations)?
>
>> Page 3 Col 1 Lines 42-45. **Possibly, a clarification should be added: instead "... with other NN methods" use " ... with previosuly determined best LSTM with Attention model."**
>>

> Paragraph 2.2 could be reduced and summarized as LSTM is well-known in literature.
>
>> **Removing that figure would be useful. Sizing of Figure 3 ruins layout.** The content starting from Page 3 Col 2 Line 14 - 34 has been removed, with the explanation used in the thesis. As the results, all the explanation were shifted to Page 3, with Page 4 dedicated to Figure 4, followed by exact explanation.
>>

> There are plenty of images that were also used in a previous paper (that is [23]) which are different in the real implementation, as it is also mentioned by the authors. The correct figures for the real implementation should be provided. Moreover, in Figure 5 there is a possible mistake in the output values SoC_(s), SoC_(s+1), SoC_(2s+1),...(Should the SoC_(s) be SoC_(1)? ). Please check and, if it is not wrong, provide further explanation of the step in which the SoC values are calculated.
>
>> (Now even I can't recall what was my reasoning for that indexation...) Page 5 Col 1 Lines 30+ **The s-step has been renamed with s-skip to match the in-text definition.**
>>

> Literature review can be improved by providing more research for models that are used for calculating the SoC of the battery (CNN with/or GRU, LSTM, BiLSTM, BiGRU) using different or CALCE dataset.
>
>> (There is a short refernece mentioning that, better not to repeat previous work). **I have to figure out how to refuse that request, especially since he mentioned "can be improved". With 2.2 removal, the text made a nice fit with figures.**
>>

> Figure 1 could be misleading: apparently data employed for validation are included in the training set. If not, please correct the image.
>
>> Indeed they are included, only to verify the state of the model and lack of any other samples. That is why validation was done on the testing data, like it is stated on the Page 2, Col 2 Lines 49-51. **Worth adding a line after 58, stating that properly. The valid area has been used as the divergence measurment to estimate how model proceeds with capturing or overfitting.** Another clarification has been introduced on Page 3 Col 1 Lines 60-61 and later in results Page 7 Col 2 Lines 35-38.
>>

> as regards Table 4, in the description text below (lines 48-49), please better clarify that employed data in the training are not the same used for the testing (even if they belong to the same cycle profile).
>
>> No, the Trained on DST and Tested on DST or with other models simply reports the training error, which has been done on the same dataset of the same cycle profile. Training values of plots Figure 9 (a,d,g)) **Going to add that clariication ther.**
>>

> in some cases acronyms are defined (as SoC for the State of Charge) but they are not consistently used. Please check along the text.
>
>> The only definition of SoC has been used in Article info an Introduction. All the remaining reuses of State of Charge were applied to avoid constant repeatence of SoC. (Need to clarify that, since when it become an issue?)
>>

> in the Bibliography, reference 22 is exceeding the column format. Please fit references to the column width.
>
>> A new line symbol has been added in the mid of the reference link in the .bbl file
>>

## Examiner 2 feedback

The novelty of the paper is not clear. The structure and content of the paper is not valued to be documented now. The format of the paper cannot warrant its publication in this journal. Some suggestions and advices are as follows:

> Improve the overall consistency and "look-and-feel" of the figures. They should have the same fonts, font size, axes formatting, etc., as is appropriate for a high-quality journal. Make sure that fonts used in figures (labels, annotations, callouts, ...) are similar in size to the fonts used in the main text and no smaller than the font size of the figure captions. Use high-resolution graphics. For example, figure 5 and figure 3 were not clear enough for the reader.
>
>> (**How about removin the titles from all plot figures, and put it to the description? Keep labels and axes as they are. That decision can be left to journal, since they are the one who modifes the quality.**) Figure 5 white borders were removed and increased in scale to 1.05, and Figure 3 removed from the context completely.
>>

> The paper title was confused. No battery appeared in the title.
>
>> **Maybe the actual batteries do not occure, like in the earlier reviewed versions of the similar articles, they surely discusses their properties, how utilised and what type of data .....**
>>

> The first reference number was 12. It was strange. The references should be indexed by sequence.
>
>> **Honestly, no clue myself why biblography gets generated in the non-ordered way. I'll figure something later**
>>

> The writing of the paper was poor. The authors should improve it before it was submitted to an academic journal.
>
>> The similar state of the paper was already went through one prof reader during the MPhil submission, as well as 9 edits with supervisor. If it is required, it can be sent to another one, from the journal, sinilar to first publication. **Although, as of the others outlined ...**
>>

## Examiner 3 feedback

The paper contains sufficient experiments and proper use of methodology.

> Should Equation (1) be RMS Error instead of ABS Error?
>
>> The error calculation on the graphs has been done with Absolute error. To avoid similarity with RMS, and avoid the reuse from previos work, the square and sqrt has been replaced with module symbol.
>>

> Table 1 demonstrates model structure and parameters, and obviously this is just a single-layer LSTM-RNN. Whether some enhancements of networks structure can further improve the effectiveness of this approach needs to be discussed.
>
>> **Something was mention siomewhere for the reasoning being not certain if multilayer implementation is correct, also that would add another area of research where I would have to determine best set of hyperparameters like it was in previous work, again... Somethign what I was afraid of, need to check the thesis description.**
>>

> A discussion of the advantages of the proposed approach needs to be added to section III or elsewhere.
>
>> **What in hell wrong with the introduction one, and the one discussing the improved results?**
>>

## Examiner 4 feedback

> The author should check whether the formula expressions are correct and the variables in the formulas should be explained.
>
>> The formula expressions are correct and were determined from the first principal, all variables are explicitly defined at the point of their definion. The LSTM cell discussion has been removed that resolved the potential issue with bariable meanings.
>>

> Figures and tables should be placed as close as possible to their corresponding textual explanations.
>
>> Text vise, Figures and Tables are located at the end of every paragraph, where they are defined for the first time, so that the order of numbering is preserved along with context. The positioning has been done with LaTeX compiler to create the best possible fit.
>> With Figure 3 removal from the text and corresponding content, the figure placement has been brought closely to their intext definitions, especially on Pages 6-9.
>>

> Additional experiments should be conducted to validate the model's performance, such as estimating SOC results at different temperatures.
>
>> Such experiment has been concluded in the results section, where each plot on Figure 9 (c,f,i) demonstrates 2 cycles for each scheduler. The Table 4 accuracies are calculated based on the entire dataset testing. Page 8 Col 1 Line 60 has been updated with "... model across the entire dataset for every temperature range are ..."  **Any further discusiion would only consume space.**
>>

> The performance of the proposed method should be compared with other methods.
>
>> Table 4, best picks from previos paper,which already compared other methods. Placing them here would only take space, worse readibility with unncecessary information, forcing reader to compare with whatever already had to be compared before.
>>
