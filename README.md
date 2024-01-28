# Rubric: AI Equity Rubric Guidelines for Developers
# Pre-Development Considerations
# Infrastructure Assessment:
An organization seeking to build or implement an AI/ML system needs to conduct an infrastructure assessment to determine what they need to successfully build an AI/ML system. The infrastructure model consists of hardware and software components that are necessary for building and training AI models. Components such as specialized processors like GPUs (hardware) and optimization and deployment tools (software) fall under the infrastructure umbrella [1]. The following considerations will help organizations and developers navigate the process. 
# Organizations
1.	Big Data Storage: 
This refers to the ability to scale storage as the volume of data grows. The ability to handle storage should be a high priority.  This includes ensuring the proper storage capacity, Input/Output Operations per sec (IOPS) and reliability to deal with the massive data amounts required for effective AI [2]. One important factor to consider is the nature of the source data. AI applications depend on source data, so an organization needs to know where the source data resides and how AI applications will use it [2]. Organizations also need to put in place plans for monitoring and expansion as databases grow over time. Consider Cloud or On-premises solutions. Organizations must decide whether to adopt a cloud-based AI/ML solution or develop an on-premises infrastructure. 
2.	Networking Infrastructure:
The network infrastructure is a key component of the AI/ML system implementation process. To provide the high efficiency at scale required to support AI and machine learning models, organizations will likely need to upgrade their networks [2]. Optimal network infrastructure should have the following key attributes of high-bandwidth, low-latency and elastic architectures that can respond flexibly to computing needs. 
3.	Computing Resources:
It is imperative to have robust computing resources by deciding on the right mix of CPU and GPU chips. CPU-based compute units work best for light AI/ML loads while GPU -based compute units work best for advanced AI/ML workloads and neural network computing [2]. 
4.	Data Management and Governance:
Data management strategy needs to ensure that users -- machines and people -- have easy and fast access to data and it should be accessible from a variety of endpoints, including mobile devices via wireless networks [2]. Privacy and security controls need to be implemented for data access controls to comply with legal regulations about data and privacy protection. Develop a robust data governance framework that outlines data collection, storage, usage, and protection practices. Address privacy, security, and ethical concerns associated with AI/ML adoption [3]

# Developers
5.	Define Clear Objectives:
 Clearly articulate the business objectives you aim to achieve through AI/ML implementation. Identify specific problems or opportunities that can be addressed effectively using these technologies [3]
6.	Evaluate Data Availability and Quality: 
Assess the availability, quality, and relevance of your organization's data. Ensure that you have enough high-quality data to train AI models and derive meaningful insights [3]
7.	Establish Data Governance Framework:
 Develop a stringent data governance framework that outlines data collection, storage, usage, and protection practices. Address privacy, security, and ethical concerns associated with AI/ML adoption [3]
8.	Assess Infrastructure and Resources: 
Evaluate your organization's existing IT infrastructure and computing resources. Determine if you have the necessary hardware, software, and storage capabilities to support AI/ML workloads effectively depending on the application/s been considered [3]

# References:
1. https://www.redhat.com/en/topics/ai/ai-infrastructure-explained
2. https://www.techtarget.com/searchenterpriseai/feature/Designing-and-building-artificial-intelligence-infrastructure
3. https://www.linkedin.com/pulse/essential-checklist-before-adopting-aiml-your-ragu

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
