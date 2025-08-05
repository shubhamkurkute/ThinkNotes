Pipelines provide an organized approach to managing the data preprocessing and modelling code. They combine the preprocessing and modelling steps into single streamlined process.
- Cleaner Code
- Fewer Bugs
- Easier to productionize

#### Important points to remember
-  A pipeline is sequence of data transformers that can include a final predictor.
- It allows to apply multiple preprocessing steps to the data and optionally end with a predictor for modelling 
- Each intermediate step in the pipeline must have a fit and transform methods, while the final step only needs a fit
- The hyperparameters for any step can be set by using its name followed a double underscore __ and the parameter name.