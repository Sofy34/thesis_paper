# Reviewers remark
bullet 1. Are the objectives and the rationale of the study clearly stated?


|1|. the task of narrative detection, as stated by the authors is a non-standard task in natural language processing . Authors should then spend effort to a) compare to existing similar tasks in the NLP community and b) elaborate how their task is different. Last but not least they should describe it clearly right from the beginning of the paper.

|2|. Moreover the example provided in section 3.1 are not convincing and in general they should be processed through a thorough annotation process.

|3|. 2) Given the opportunity of this NLP task to have impact on a machine-aided experience, authors are encouraged to consider extrinsic evaluation methodologies and metrics.

bullet 2. If applicable, is the application/theory/method/study reported in sufficient detail to allow for its replicability and/or reproducibility?

|4| Most serious issue is the methodological approach to the corpus annotation. Authors are not using best practices and known techniques to consider the linguistic phenomena of conversational speech and how to deal with them by setting appropriate annotation guidelines. The speech transcription guidelines are not disclosed or described. The operational definition of a sentence or paragraph is not disclosed.

|5| At a higher level, the NLP task is not positioned with respect to the original motivation of the research, that is supporting psychotherapists in their practice.

bullet 3 If applicable, are statistical analyses, controls, sampling mechanism, and statistical reporting (e.g., P-values, CIs, effect sizes) appropriate and well described?

|6| The authors provide sufficient results and analysis given the exploratory Machine Learning based nature of the manuscript. However, the sample size is very limited. They highlight it's "a dataset of 38434 sentences" but those sentences are not independent. Their dataset only consists of 79 psychotherapy sessions. The sentences within each session and their corresponding labels are highly dependent to each other. This is a point that the authors should focus more throughout the manuscript and make it clear in the introduction / conclusion.

|7| This becomes even trickier since the authors modify the F1 score specifically based on the dependence of the samples. As the mention, "if the model recognized a narrative boundary one sentence prior or one sentence subsequent to the precise narrative boundary point, the predicted label would still be regarded as accurate".

bullet 4. Could the manuscript benefit from additional tables or figures, or from improving or removing (some of the) existing ones?

|8| a. It would probably be easier for the reader if (some of) the data statistics provided in section 4.1 are provided in a Table.

|9| b. In Figure 5, instead of "baseline" I would suggest using the label "baseline (TF-IDF)", since the authors have used three different baselines, so it can be confusing.

bullet 5. If applicable, are the interpretation of results and study conclusions supported by the data?

|10|
Provide further comments here:
Experiments are missing a strong baseline such as a classifiers using label priors.
|11| Error analysis is not satisfactory
|12| It is not clear how the sentence-level decision have been integrated across

|13|
The authors suggest a machine learning model, do some ablation studies and analyze their results. Even though the analysis and results are clear, there are some points which need attention/revision:

a. The authors compare their BERT model vs their CRF model and they justify the superior results of the CRF primarily based on the fact that BERT considers "each sentence as an isolated unit". However, this is true only because of the particular way that BERT was used. The authors could have used a model where BERT provides an embedding and this embedding is then the input to a CRF. This by itself would be a great additional experiment the authors could consider in order to evaluate the extra value of their feature vector ("sequence assemble").

|14|
b. Te authors compare their result to another study [22] (page 18) on a "comparable task", simply by providing the numerical result of the citation. This is not a valid comparison of the different methods, since they are applied on different datasets. It is very probable that the proposed method would yield very different results if applied to the dataset of [22]. For the same reason, the numbers (F1 scores) the authors provide in Section 2 do not actually provide any valuable information to the reader since they refer to different tasks and datasets.

bullet 6. Have the authors clearly emphasized the strengths of their study/theory/methods/argument?

|15| in part they have made a convincing point about the motivation of their work, however they did non follow-up with convincing research methodology and experimental results.

bullet 7. Have the authors clearly stated the limitations of their study/theory/methods/argument?

|16| there was no such discussion

|17| Even though the authors mention as a future work the focus on a larger dataset, they should be more clear on the data size used in tis particular study (please see Q. 3)

bullet 8. Does the manuscript structure, flow or writing need improving (e.g., the addition of subheadings, shortening of text, reorganization of sections, or moving details from one section to another)?

|18| The main problem with the structure of the text is the usage of too many paragraphs; in some cases even one sentence is a paragraph.

bullet 9. Could the manuscript benefit from language editing?

This is a well-written manuscript on an interesting topic. Apart from the comments in the questions above, here are some additional comments and suggestions:

|19| a. Section 2: The authors could consider adding some references where the psychotherapy session is viewed under the viewpoint of a narrative / story. E.g.:
V.R. Martinez, N. Flemotomos, V. Ardulov, K. Somandepalli, S.B. Goldberg, Z.E. Imel, D.C. Atkins, S. Narayanan, Identifying therapist and client personae for therapeutic alliance estimation, Proceedings of Interspeech 2019, pp. 1901-1905

|20| b. It is not very clear why the authors choose the unconventional normalization of converting all the digits to "123". Wouldn't an implicit distinction (by not normalizing) of numbers eg in representing money vs. representing dates (1,000 would be valid for the first but not for the second) potentially provide valuable information to the algorithm?

|21| c. Probably the "deletion of timestamps" is a step not necessary to be mentioned in the main text of the manuscript (I believe this is expected/default even without mentioning)

|22| d. Why did the authors choose sequence of characters as ngrams and not sequences of words (which is much more common nowadays in natural language processing)?

|23| e. Why the binary features (eg speaker marks) are in {0, 0.5} and not {0, 1}?

|24| f. Section 3.2.3: What is a "sequential load format"?

|25| g. Why are 4 features necessary and not 2 for the ensemble? Isn't the case that "non-narrative label" = 1 - "narrative label" ?

|26| h. Section 3.2.7: Simply a suggestion: The authors could consider explaining their smoothing approach using the formalization of morphological operators. Specifically, it seems they are normalizing their indicator function using a morphological closure followed by a morphological opening. For some details, please see Section 6 of
G. Evangelopoulos, A. Zlatintsi, G. Skoumas, K. Rapantzikos, A. Potamianos, P. Maragos, Y. Avrithis, VIDEO EVENT DETECTION AND SUMMARIZATION USING AUDIO, VISUAL AND TEXT SALIENCY, 2009 IEEE International Conference on Acoustics, Speech and Signal Processing, pp. 3553-3556

|27| i. Section 11, page 11: evaluation parameters --> evaluation metrics

|28| j. Section 4.1. What is defined as a "paragraph" in a transcript?

|29| k. Section 4.4.1: This baseline classifier operates by assigning all instances to their true labels --> This baseline classifier operates by assigning all instances to true labels (if I understand correctly what the classifier does)
 



