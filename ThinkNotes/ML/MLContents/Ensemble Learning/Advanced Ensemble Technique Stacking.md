## Stacking
Stacking combines multiple classification or regression models via a meta model which could be a meta classifier or a meta regressor. After training the base models on the complete dataset, the meta-model trains on the base models outputs as features, to give a final prediction. This technique leverages the strengths of each base model and can achieve higher accuracy.
- In stacking as opposed to bagging a  variety of models (not solely decision trees) are employed, all which are trained in the same full dataset rather than on subsets.
- Unlike boosting, in stacking a single model is used to learn how to best combine the predictions from the contributing models (e.g. instead of a sequence of models that correct the predictions of prior models).
- 
![link text](https://labcontent.simplicdn.net/data-content/content-assets/Data_and_AI/ML/updated/Lesson_05/image7.png)

  

- Stacking aims to leverage the advantages of different base models by inputting their predictions into a meta-model. The structure of a stacking model consists of multiple base models, also known as level-0 models, alongside a meta-model that integrates their predictions, known as the level-1 model.
* Level-0 Models (**Base Models**): These models are trained on the full training dataset, and their individual predictions are aggregated.
* Level-1 Model (**Meta-Model**): This model is designed to optimally combine the predictions of multiple base models to generate the final prediction.

__Advantages of Stacking__
- Accomplishes greater accuracy than simplistic ensemble techniques
- Enables diversity among models
- Possesses the capability to rectify errors made by base models
  
__Disadvantages of Stacking__
- Is more challenging to implement and comprehend
- Poses a risk of overfitting the meta-model
- Requires careful selection of both base and meta-models