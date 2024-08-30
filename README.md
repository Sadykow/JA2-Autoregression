# Feed-Forward State of Charge Estimation of LiFePO$_4$ Batteries Using Time-Series Machine Learning Prediction with Autoregressive Models
The Latex based source code for the second Journal article published in Journal of Energy Storage **Volume 100, Part A**.

Code compatible with Overleaf and gets built with `pdflatex`.
Majority of the figures were generated from work Python code in SVG format using `matplotlib` library.
All edits, structure sorting and Feedback from examinors have been preserved in corresponding Markdown files.

## Citation and PDF
The full citation and output PDF can be found on the publication page with the following citation:

Marat Sadykov, Sam Haines, Geoffrey Walker, David William Holmes. Feed-forward State of Charge estimation of LiFePO4 batteries using time-series machine learning prediction with autoregressive models, *Journal of Energy Storage*, Volume 100, Part A, **2024**, 113516, ISSN 2352-152X, [https://doi.org/10.1016/j.est.2024.113516](https://doi.org/10.1016/j.est.2024.113516 "Article Location").

## List of Authors:
[MPhil Marat Sadykov (First Author)](https://orcid.org/0000-0002-6436-7069)

MPhil Sam Haines

[Pr Geoff Walker](https://orcid.org/0000-0001-8137-9507)

[Pr David Holmes (Corresponding Author)](https://orcid.org/0000-0002-2970-9158)

## Additional tools:
* [most_common_words.bash](most_common_words.bash) is used as a tool to identify keywords of the article.
* The diagram of the Cells were created using Googles [draw.io](draw.io).
* The GIMP source file is provided for the landscape figure.

## Abstact:
This paper presents a Recurrent Neural Network (RNN) model for the State of Charge (SoC) estimation for an Electric Vehicle’s Lithium-Ion battery. A new Autoregressive modification is proposed to improve upon earlier published Machine Learning models to enhance the prediction accuracy and make results less sensitive to varying usage conditions. By building upon earlier published findings, assessing several models’ ability to estimate charge using a history window of sensory data, this work proposes, implements, and reports its methods of improving accuracy by introducing the State of Charge as part of sensory inputs in a Feed-Forward manner. The method is based on the Autoregressive implementation of neural network model training, where successively calculated charge values are used as input in the subsequent predictions, but the potential inaccuracies with those predictions that might otherwise cause significant and rapid divergence are accounted for within a modified recursive training procedure. As a result, with a slight increase in training time, the accuracy of the output prediction for three different realistic charge–discharge driving profiles doubled compared to the two best previously published models. Overall, the test results have demonstrated the usability of the current model in actual driving scenarios, making such models a viable replacement to estimation approaches used in electric vehicle battery management systems.

### Keywords:
Autoregressive models; Lithium-Ion battery (Li-Ion); Long Short-Term Memory Recurrent Neural Networks (LSTM-RNNs); State of charge (SOC) estimation; TensorFlow (TF)