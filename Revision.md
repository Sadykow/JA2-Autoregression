## Decision on submission to Journal of Energy Storage

Date:	May 24 2024 06:42PM
To:	"David William Holmes" d.holmes@qut.edu.au
From:	"Journal of Energy Storage" support@elsevier.com
Subject:	Decision on submission to Journal of Energy Storage

Manuscript Number: EST-D-24-01023  

Feed-Forward State of Charge Estimation Using Time-Series Machine Learning Prediction With Autoregressive Models

Dear Associate Professor Holmes,

Thank you for submitting your manuscript to Journal of Energy Storage.

I have completed my evaluation of your manuscript. The reviewers recommend reconsideration of your manuscript following major revision. I invite you to resubmit your manuscript after addressing the comments below. Please resubmit your revised manuscript by Jun 14 2024 11:59PM.

When revising your manuscript, please consider all issues mentioned in the reviewers' comments carefully: please outline every change made in response to their comments and provide suitable rebuttals for any comments not addressed. Please note that your revised submission may need to be re-reviewed. 

To submit your revised manuscript, please log in as an author at https://www.editorialmanager.com/est/, and navigate to the "Submissions Needing Revision" folder.  

Research Elements (optional)
This journal encourages you to share research objects - including your raw data, methods, protocols, software, hardware and more – which support your original research article in a Research Elements journal. Research Elements are open access, multidisciplinary, peer-reviewed journals which make the objects associated with your research more discoverable, trustworthy and promote replicability and reproducibility. As open access journals, there may be an Article Publishing Charge if your paper is accepted for publication. Find out more about the Research Elements journals at https://www.elsevier.com/authors/tools-and-resources/research-elements-journals?dgcid=ec_em_research_elements_email.

Journal of Energy Storage values your contribution and I look forward to receiving your revised manuscript.

Kind regards,  
Luisa F. Cabeza  
Editor-in-Chief  

Journal of Energy Storage

Editor and Reviewer comments:

### Reviewer #1:

Dear Authors,

in the paper "Feed-Forward State of Charge Estimation Using Time-Series Machine Learning Prediction With Autoregressive Models" a Recurrent Neural Network model for the State of Charge
estimation for an Electric Vehicle's Lithium-Ion battery is investigated using an open dataset (CALCE). Authors present the novel idea of Autoregression implemented in the LSTM model during the training procedure.
Although the paper is well written amd the genearl idea is clear, some aspects should be improved, expecially clarifying the actual implementation in real time application of the proposed methodology.
Here are some remarks:

1. In real-time applications how does the information of the true initial SoC, which is used to make the first estimation, will be known (as an error in those values might lead to serious divergences in the model estimations)?
2. Paragraph 2.2 could be reduced and summarized as LSTM is well-known in literature.
3. There are plenty of images that were also used in a previous paper (that is [23]) which are different in the real implementation, as it is also mentioned by the authors. The correct figures for the real implementation should be provided. Moreover, in Figure 5 there is a possible mistake in the output values SoC_(s), SoC_(s+1), SoC_(2s+1),...(Should the SoC_(s) be SoC_(1)? ). Please check and, if it is not wrong, provide further explanation of the step in which the SoC values are calculated.
4. Literature review can be improved by providing more research for models that are used for calculating the SoC of the battery (CNN with/or GRU, LSTM, BiLSTM, BiGRU) using different or CALCE dataset.
5. Figure 1 could be misleading: apparently data employed for validation are included in the training set. If not, please correct the image.
6. as regards Table 4, in the description text below (lines 48-49), please better clarify that employed data in the training are not the same used for the testing (even if they belong to the same cycle profile).

Minor comments:

- in the abstract please avoid using the reference link to a previous publication ([...] upon earlier published findings, assessing several models ability to estimate SoC using a history window of sensory data (Sadykov et al [23]), this work proposes [...]), it would be better rephrasing or simply erasing the reference.
- usually in the abstract is preferable not to use acronyms.
- in some cases acronyms are defined (as SoC for the State of Charge) but they are not consistently used. Please check along the text.
- in the Bibliography, reference 22 is exceeding the column format. Please fit references to the column width.

For these reasons a Major revision is required.

Best regards

### Reviewer #2:

Comments to Author.
The authors proposed a Recurrent Neural Network model for the State of Charge estimation for an Electric Vehicle's Lithium-Ion battery. Even rough a lot of works were carried out. The novelty of the paper is not clear. The structure and content of the paper is not valued to be documented now. The format of the paper cannot warrant its publication in this journal. Some suggestions and advices are as follows:

1) Improve the overall consistency and "look-and-feel" of the figures. They should have the same fonts, font size, axes formatting, etc., as is appropriate for a high-quality journal. Make sure that fonts used in figures (labels, annotations, callouts, ...) are similar in size to the fonts used in the main text and no smaller than the font size of the figure captions. Use high-resolution graphics. For example, figure 5 and figure 3 were not clear enough for the reader.
2) The paper title was confused. No battery appeared in the title.
3) The abbreviation was disordered. Some abbreviation is explained several times. It is presented only for the first time when it appeared, then the abbreviation should be used instead of the full name. If the abbreviation had been explained in the abstract. The author can use it directly in the text of the paper.
4) The first reference number was 12. It was strange. The references should be indexed by sequence.
5) The writing of the paper was poor. The authors should improve it before it was submitted to an academic journal.

### Reviewer #3:

Comments to Author.
In this paper, authors present a new Recurrent Neural Network model for the State of Charge estimation for Lithium-Ion battery. Using Feed-Forward Autoregressive and adding the SOC as an extra feature that can enhance the prediction accuracy. The paper contains sufficient experiments and proper use of methodology. But the following issues need to be addressed before the article can be published

(1) In introduction, could a table be added to show more clearly the general review of the application of machine learning methods to SOC estimation.
(2) The author's contribution and the specific problem being addressed should be listed in an organized manner at the end of the introduction.
(3) Should Equation (1) be RMS Error instead of ABS Error?
(4) The quality of Figure (5) and Figure (7) is poor, which needs to be improved.
(5) Table 1 demonstrates model structure and parameters, and obviously this is just a single-layer LSTM-RNN. Whether some enhancements of networks structure can further improve the effectiveness of this approach needs to be discussed.
(6) A discussion of the advantages of the proposed approach needs to be added to section III or elsewhere.

### Reviewer #4:

This paper presents a Recurrent Neural Network model for the State of Charge estimation for an Electric Vehicle's Lithium-Ion battery. A new Autoregressive modification is proposed to improve upon earlier published Machine Learning models to enhance the prediction accuracy and make results less sensitive to varying conditions.This reviewer has the following comments:

1. The contributions in Introduction section are also very generic. Please provide concrete quantitative findings to highlight how the paper addresses the current problem.
2. The author should check whether the formula expressions are correct and the variables in the formulas should be explained.
3. The author should increase the resolution of some of the images to achieve a uniform resolution throughout the document.
4. The author should carefully review the manuscript, for example, Figure 5 is not displayed in the manuscript.
5. Diagrams should be added to illustrate the workflow of the proposed methods for better understanding.
6. Figures and tables should be placed as close as possible to their corresponding textual explanations.
7. Additional experiments should be conducted to validate the model's performance, such as estimating SOC results at different temperatures.
8. The introduction mentions GRU; therefore, why was LSTM chosen as the research object instead of the GRU network?
9. The performance of the proposed method should be compared with other methods.

### More information and support 

FAQ: How do I revise my submission in Editorial Manager?
https://service.elsevier.com/app/answers/detail/a_id/28463/supporthub/publishing/

The journal’s policy on requests of changes to authorship is as follows:
Authorship should be limited to those who have made a significant contribution to the conception, design, execution, or interpretation of the reported study.  All those who have made substantial contributions should be listed as co-authors.

Authors are expected to consider carefully the list and order of authors before submitting their manuscript and provide the definitive list of authors at the time of the original submission. Only in exceptional circumstances will the Editor consider (at their discretion) the addition, deletion or rearrangement of authors after the manuscript has been submitted and the author must clearly flag any such request to the Editor.

Adding, deleting or rearranging authors after the manuscript has been submitted without satisfactory explanations will lead to rejection or withdrawal of the manuscript at any stage before or after the paper is accepted.

You will find information relevant for you as an author on Elsevier’s Author Hub: https://www.elsevier.com/authors

At Elsevier, we want to help all our authors to stay safe when publishing. Please be aware of fraudulent messages requesting money in return for the publication of your paper. If you are publishing open access with Elsevier, bear in mind that we will never request payment before the paper has been accepted. We have prepared some guidelines (https://www.elsevier.com/connect/authors-update/seven-top-tips-on-stopping-apc-scams ) that you may find helpful, including a short video on Identifying fake acceptance letters (https://www.youtube.com/watch?v=o5l8thD9XtE ). Please remember that you can contact Elsevier s Researcher Support team (https://service.elsevier.com/app/home/supporthub/publishing/) at any time if you have questions about your manuscript, and you can log into Editorial Manager to check the status of your manuscript (https://service.elsevier.com/app/answers/detail/a_id/29155/c/10530/supporthub/publishing/kw/status/).
#AU_EST#

To ensure this email reaches the intended recipient, please do not delete the above code

### Reviewer #2

The authors had revised the paper according to four reviewer's advices and suggestions. All the concerns from the reviewer had been addressed. I am agreed with the point-to-point response for my concerns. After the revision, the paper had sufficient material in terms of novelty and technical quality that warrant publication in this high-level journal. The format of the paper can warrant its publication in this journal also. It is valued to be documented in my opinion. Some minor suggestions and advices are as follows:

1. The format of the paper should be improved continuously.
2. The title of figure 4 was too long. The explanation should be moved into the text.
3. The indexed reference number was [7, 8, 6], why? What is the Correspondence relationship?

### Reviewer #3

As a result of the author's revisions, some of the errors and content in this paper were resolved. This paper became more logical, but there are still issues that need to be addressed before publication:

1. In response to my previous question 4, the authors did not revise the figure, where Fig. 6 is significantly less clear than the others, and therefore needs to be revised. Not modify the content of the figure, but increase the clarity quality of the image.
