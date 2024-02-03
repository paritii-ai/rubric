# Post Development
  # Ensure model is human interpretable:
  The simplest way to ensure models are interpretable is to use models which by their design are interpretable[1]. The class of models which are apriori interpretable are Linear regression, logistic regression and decision trees. Neural network models commonly used in deep learning are not by design easily interpretable but techniques exists to ensure interpretability. Interpretability facilitates[2]:
1. Understanding 
2. Debugging and auditing ML model predictions 
3. Bias detection to ensure fair decision making 
4. Robustness checks to ensure that small changes in the input do not lead to large changes in the output 
5. Methods that provide recourse for those who have been adversely affected by model predictions 

Depending on the model complexity, methods for model interpretability can be classified into intrinsic analysis and post hoc analysis.Intrinsic analysis can be applied to interpret models that have low complexity (simple relationships between the input variables and the predictions) while post hoc analysis can be applied to interpret simpler models as well as more complex models, such as neural networks, which have the ability to capture non-linear interactions [2]. These methods are often model-agnostic and provide mechanisms to interpret a trained model based on the inputs and output predictions. Post hoc analysis can be performed at a local level, or at a global level [2]. An AWS white paper provides a detailed explanation of the various techniques for model interpretability and can be accessed here (https://docs.aws.amazon.com/whitepapers/latest/ml-best-practices-healthcare-life-sciences/model-interpretability.html)
 # References:
1. https://christophm.github.io/interpretable-ml-book/simple.html
2. https://docs.aws.amazon.com/whitepapers/latest/ml-best-practices-healthcare-life-sciences/model-interpretability.html

 # Avoid bias evolving in the learning model over time:
 Bias in machine learning models refers to systematic errors introduced by algorithms or training data that lead to unfair or disproportionate predictions for specific groups or individuals [1]. Such biases can arise due to historical imbalances in the training data, algorithm design, or data collection process [1]. You avoid bias evolving in the ML model over time by assesing several metrics and methodologies used to assess bias namely [1];
- Disparate Impact Analysis: This technique examines the disparate impact of an AI model's decisions on different demographic groups. It measures the difference in model outcome for various groups and highlights potential biases.
- Fairness Metrics: Different fairness metrics have been developed to measure bias in machine learning models. Key examples include Equal Opportunity Difference, Disparate Misclassification Rate, and Treatment Equality. These metrics help assess how fairly the model treats different groups. 
- Post-hoc Analysis: This involves examining an AI system’s decisions after deployment to identify instances of bias and understand its impact on users and society.
# References:
1. https://encord.com/blog/reducing-bias-machine-learning/

# Versioning and Proper Documentation on Model Design and Implications:
Versioning management tools like Github and Bitbucket exist to manage software development versioning and documentation. Machine learning models which are basically a complex ecosystem of data, algorithms and code also require versioning and documentation. Version Control is the process of tracking and managing software changes over time. Whether you’re building an app or an ML model, you need to track every modification done by members of the software team to fix bugs and avoid conflicts [1]. The machine learning development process requires a lot of iterative work, where the developers and Data Scientists are searching for the best performing model while changing hyperparameters, code, and data. It is therefore important to keep a history of these changes to track model performance relative to the parameters, which saves you the time you would spend retraining the model for experimentation or deployment purposes [1]. 

Machine learning version control has three parts [1]:

A. Code
There is modelling code and implementation code. Modelling code is used to implement the model, and implementation code is used for inference. They can both be written in different programming languages, but it might make it more difficult to maintain all of your code and dependencies. 

B. Data
There is metadata, which is information about your data and model. Then there is the actual data, the datasets that you use to train and run your model. Metadata can change without any change in the data, and versioning should link the data to the appropriate meta information

C. Model
The model is the glue that connects all of the above with model parameters and hyperparameters to produce a finished product.

Versioning models and data creates a framework for better monitoring of the models. In addition, versioning serves as an accelerator on how frequently the models can be updated and placed in production [2]. With proper versioning and documentation, we can combine model predictions and the corresponding input data with model versions and trained data. With this kind of logical grouping, we can eventually detect data drifts and model miss performances which then allow for better model retraining and troubleshooting [2].
More information about version and proper documentation can be found in this excellent resource here (https://neptune.ai/blog/version-control-for-ml-models)
# References:
1. https://neptune.ai/blog/version-control-for-ml-models
2. https://www.silo.ai/blog/versioning-transparency-monitoring-in-machine-learning-pipelines


# Data Retention and Deletion Strategy for Handling Ethical and Privacy Issues:
Data retention is the storing of information for a specific period of time. It helps businesses reduce costs, legal risks, and security threats to users and organizations [1]. To successfully implement a data retention policy, incoming and existing data needs to be properly classified and organized based on its risk level and intended use [1]. The data retention policy needs to indicate who and which departments are responsible for the retention and disposal of each data type in the data ecosystem. The policy should also state what needs to happen at the end of the retention period [1]. Many global privacy regulations have demanded that organizations and instituitions make data deletion a common practice, rather than just a best practice [2]. There are two types of data deletion processes required by privacy regulations namely request-based deletion and data retention and purge [2]. Request-based deletion is initiated  when someone initiates a data deletion request. The individual's status and relationship with the organization determine whether the request must be honored, what type of data can be deleted upon the request, and whether any exceptions to deletion requirements apply. Data deletion exceptions can include retaining data that is required for service delivery, legal and regulatory reasons, or financial reporting [2]. Data retention and purge are more focused on deleting data according to an organization’s schedules and internal process guidelines. This requires organizations to operate a dedicated data retention governance team to provide data retention and purge oversight in order to deal with ethical and privacy issues. A  sustainable data deletion program can help organizations improve their compliance with applicable privacy and data protection requirements as well as enhance data governance and data protection posture at the same time [2].

# References:
1. https://segment.com/blog/data-retention/
2. https://www.grantthornton.com/insights/articles/advisory/2020/how-data-deletion-empowers-data-protection

# Continuous Fairness Monitoring of ML Models:
ML fairness and monitoring are increasingly becoming critical components of machine learning in the wake of demands for equity and diversity in AI products. ML practitioners generally regard monitoring for drift as an early warning system for performance issues and evaluating models with fairness metrics as a solution for assessing bias in a trained model [1]. A trained model that is fair can become unfair after deployment due to the same model drift that causes performance issues [1]. A method to measure and monitor fairness in ML models over the model lifecycle is Quantile Demographic Drift (QDD) [2]. QDD is a novel model bias quantification metric that uses quantile binning to measure differences in the overall prediction distributions over subgroups [2].  QDD is incorporated into a continuous model monitoring system, called FairCanary, that reuses existing explanations computed for each individual prediction to quickly compute explanations for the QDD bias metrics [2]. When unfairness is detected, a bias mitigation strategy replaces the score of the disadvantaged group with the score of the corresponding rank in the advantaged group [2]. As this approach is a post processing step, it avoids pretraining to debias the model and is therefore a computationally inexpensive approach to bias mitigation [2]. More information about continous fairness monitoring can be found in this paper here (https://arxiv.org/abs/2106.07057)

# References:
1. https://www.fiddler.ai/blog/faircanary-rapid-continuous-explainable-fairness
2. Avijit Ghosh, Aalok Shanbhag, Christo Wilson. FairCanary: Rapid Continuous Explainable Fairness (https://arxiv.org/abs/2106.07057)

# Evaluate Algorithms and Output for Bias:
Algorithmic bias occurs when AI/ML model design, data, and sampling result in measurably different model performance for different subgroups [1]. The two major courses of algorithmic bias are subgroup invalidity and label choice bias. Subgroup invalidity occurs when AI/ML is predicting an appropriate outcome or measure, but the model does not perform well for particular subgroups [1]. The underlying cause is when AI/ML models are trained on non-diverse populations or with data that underrepresents the subgroup or fails to include specific risk factors affecting them [1]. Label choice bias occurs when the algorithm’s predicted outcome is a proxy variable for the actual outcome it should be predicting [1].
The following steps can be taken to evaluate algorithms and output for bias [1,2]. 

A. Examine the data for problems related to lacking diversity and poor performance for underserved groups. Confirm that the data on which the models are trained is representative of the populations to which they will be applied. Consider how subgroups are defined and the fraction of each subgroup relative to the total population. If definitions differ from the training set to your population, the model may be potentially biased.

B. Measure performance in each subgroup to ensure models are well calibrated and do not perform worse for any particular group. But note that, good performance across subgroups does not guarantee a lack of bias, but it is a key step to avoiding it.

C. Establish processes to systematically evaluate the potential for label choice bias with multiple stakeholders and also attempt to ensure the labels used in training data align with your organization’s intended use.

D. Assess inputs and outputs of each algorithm and determine whether they are susceptible to or demonstrate bias. Pay close attention to whether proxies that an algorithm uses could introduce bias. Articulate the algorithm’s ideal target vs. its actual target.

E. If bias is detected in an algorithm, find a way to improve it, such as retraining it with more data or predicting a slightly different outcome.

# References:
1. https://www.closedloop.ai/blog/four-steps-to-measure-and-mitigate-algorithmic-bias-in-healthcare/
2. https://www.aha.org/aha-center-health-innovation-market-scan/2021-10-05-4-steps-mitigate-algorithmic-bias

# Potential impact assessment of Output:
It is imoprtant to practically test the output of a machine learning model prior to human interpretation. There are three testing methods that can be used, namely [1];

1. Invariance Test - The invariance test defines input changes that are expected to leave model outputs unaffected. A common method for testing invariance is related to data augmentation. You pair up modified and unmodified input examples and see how much this affects the model output.
2. Directional Expectation Test - A directional expectation test is a test which is run to check hpw a change in the input distribution changes the expected output. An example is  testing assumptions about the number of bathrooms or property size when predicting house prices. A higher number of bathrooms should mean a higher price prediction. Seeing a different result might reveal wrong assumptions about the relationship between our input and output or the distribution of our dataset.
3. Minimum Functionality Test - The minimum functionality test helps you decide whether individual model components behave as expected. The reasoning behind these tests is that overall, output-based performance can conceal critical upcoming issues in your model. A few ways to do this are, create samples that are “very easy” for the model to predict, in order to see if they consistently deliver these types of predictions; test data segments and subsets that meet a specific criteria; test for failure modes you have identified during manual error analysis.
# Reference:
1. https://deepchecks.com/how-to-test-machine-learning-models/

# Practical Ways of Mitigating Biases in the Use of the Output (Misuse, Misaligned use, and Misinterpretation of the Output):
AI developers who develop ML models in order to mitigate biases in the output can follow the suggestions to include a “model facts label”, i.e., a 1-page of relevant and actionable information to ensure that front-line users know how, when, how not to use the output [1]. The model facts label can include a short summary about the AI system, the working mechanism (including the source and baseline characteristics of data used for AI development), results of validation studies, guidelines for use (including benefits and appropriate decision support), warnings (including potential risks and consequences), and other relevant information related to the AI system [1]. 
Another practical technical way of mitigating bias is to use the eqaulized odds post-processing. This is a post-processing technique that solves a linear program to find probabilities with which to change output labels to optimize equalized odds [2]. A Python implementation of this technique can be found here (https://aif360.readthedocs.io/en/v0.2.3/modules/postprocessing.html)


# References:
1. Cristina González-Gonzalo, Eric F. Thee, Caroline C.W. Klaver, Aaron Y. Lee, Reinier O. Schlingemann, Adnan Tufail, Frank Verbraak, Clara I. Sánchez,Trustworthy AI: Closing the gap between development and integration of AI systems in ophthalmic practice, Progress in Retinal and Eye Research,Volume 90,2022,101034,ISSN13509462, https://doi.org/10.1016/j.preteyeres.2021.101034(https://www.sciencedirect.com/science/article/pii/S1350946221000951).
2. https://aif360.readthedocs.io/en/v0.2.3/modules/postprocessing.html

# How to Evaluate Algorithms and Output for Bias:
Algorithmic bias has the potential to cause serious harm and even have life-threatening impact on consumers of the output of ML/AI models. Hence, there is a practical need to evaluate algorithms and output for bias. There are a few steps that can be implemented namely[1];
A. Inventory of algorithms - Maintain a detailed inventory of all algorithms being used or developed. Include information such as the purpose, functionality, development stage, and key components. Form a diverse committee comprising internal and external stakeholders, including subject matter experts, data scientists, legal experts, and ethicists. This committee should meet regularly to discuss algorithmic developments, ethical considerations, and potential impacts.
B. Screen each algorithm for bias - Some general steps that you can take to screen algorithms for bias are as follows
      - Define Bias: Clearly define what bias means in the context of your application. Bias can manifest in various ways, such as 
         racial, gender, or socioeconomic bias.
      - Diverse Dataset: Ensure that your training dataset is diverse and representative of the population your algorithm is intended to 
        serve. Biased training data can lead to biased models.
      - Data Preprocessing: Carefully preprocess and clean the data to remove any existing biases. Be aware of potential biases 
       introduced during data collection or labeling.
      - Fair Features: Identify and analyze the features used by the algorithm. Check for any features that may disproportionately 
        impact 
       certain groups and assess their relevance.
      - Regular Audits: Conduct regular audits of the algorithm's output to detect any patterns of bias. This includes monitoring for 
       disparate impacts on different demographic groups.
      - Bias Metrics: Develop and use specific metrics to measure bias. Metrics such as disparate impact, equalized odds, and 
        demographic parity can help quantify and identify bias.
      - Post-Processing Techniques: Implement post-processing techniques to mitigate bias. This can include re-ranking or re-scoring 
        algorithmic outputs to achieve fairness.
On the technical side, python libraries like Aequitas (http://aequitas.dssg.io/) can be used to test for bias in the features and output of the algorithm 
Encourage users to provide feedback on the algorithm's outputs, especially if they believe bias may be present. This feedback loop can be valuable for continuous improvement.

# References:
1. https://www.aha.org/aha-center-health-innovation-market-scan/2021-10-05-4-steps-mitigate-algorithmic-bias
2. http://aequitas.dssg.io/

