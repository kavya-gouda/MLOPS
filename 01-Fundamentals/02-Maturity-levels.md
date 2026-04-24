# Maturity Levels in MLOPS
 It is not easy to implement the fully matured pipeline in organizations, very rare companies have reached to that maturity level. as a thumb rule, the level of automation of the steps in a ML process defines the maturity of it. in this article, we will be discussing about the various maturiy level known in MLOPS.
 
 if we achieved the automation of an orchestrated experiment then we can say we are one-level mature, then when some other automation is achieved then you are two-levels mature, like this till the full automation.

Let us now see what the recognized maturity levels in machine learning culture are, and after what automation we say that we have achieved a certain level of maturity. 

usually there are three recognized levels of MLOps.

These three levels are not some hard and fast rule. Actually, it is up to you to define. You can create N number of levels and define the amount of automation in each level. Google has classified automation in three levels, while Microsoft Azure has defined up to five maturity levels. So it is as per need basis. Anyways, I will define three levels and categorize each of the maturity level based on few parameters like teams involved in it, data gathering strategy, development activities, model release, CI/CD, application integration, and monitoring.


- MLOPS Level 0
- MLOPS level 1
- MLOPS level 2

## MLOPS Level 0
<img width="455" height="356" alt="image" src="https://github.com/user-attachments/assets/7bf01b08-78ae-4877-b72b-6ca02b5e08db" />

Let us start with the MLOps level zero, which is considered as a basic level of maturity and is totally a manual process, therefore, it is also called no MLOps at all, as it is the same traditional machine learning lifecycle. So first category to define is People.

1. data scientists and ML researches build state of the art models, but the process for building and deploying ML models is entirely manual. Data scientists are siloed and they are not in regular communication with the operations team. This process separates the data scientist who create the model, and engineers who serve the model as prediction service. The data scientist handover trained model as an artifact to the engineering team to deploy on their API infrastructure.
2. Then Data gathering. At this level, data assets are often scattered throughout the applications such as email, spreadsheets, and purpose-built databases, that make achieving a holistic view of the data impossible. Interestingly, many companies don't even know  what data they own. It's like saying, "Hey, I have some data available somewhere, can you please dig into it and give me some valuable predictions using it?" Going to this situation, it is obvious that every step should be manual, including data gathering, data analysis, data preparation, et cetera.
3. the development activities. All the development activities of model training validation are manual and only script-driven. Data scientist run the models locally and then throw them over the wall leaving developers  and DevOps engineers to translate those models into a format that can be incorporated into applications.
4. model release. Model release is again a manual activity at this level, and it is handled by a data scientist or engineers alone. In MLOps zero, a trained model is the entity which would be deployed.
5. CI, no continuous integration in MLOps zero. because few implementation changes are assumed, so CI is ignored. And usually, testing the code is part of the notebooks or script execution.
6. CD, no continuous delivery in zero level. The process assumes that your data science team manages a few models that don't change frequently neither by changing the model implementation nor by retraining the model with new data. A new model version is deployed only a couple of times per year. Since there aren't frequent model version deployments, so CD isn't considered. Also, deployment here refers to the prediction service only. The process is concerned only with deploying the trained model as prediction service.
7. application integration and testing  is heavily reliant on data scientist expertise to implement.
8. Monitoring, lacks active performance monitoring. The process doesn't track or log the model predictions and actions which are required in order to detect model performance degradation and other model behavioral drifts.

<img width="608" height="275" alt="image" src="https://github.com/user-attachments/assets/5e7db464-9e52-4d4e-b54d-9468f5a22767" />

if we see the flow diagram of this level, this is how it will look. A pure conventional way of handling machine learning projects where there is a clear wall between machine learning and operations. All these experiment steps are manual, no CI/CD pipelines. And as part of deployment, the trained model is deployed as prediction service into production.

So guys, these were some of the characteristics of MLOps level zero. MLOps level zero is a common in many businesses that are beginning to apply machine learning to their use cases. This manual data scientist driven process might be sufficient when models are rarely changed or trained. In practice, these models often break when they're deployed in the real world. Since the models can't be trained in production environment, so they fail to adapt to changes in the dynamics of that environment. That is why you would like to jump to the next level of maturity,


## MLOPS Level 1
<img width="458" height="358" alt="image" src="https://github.com/user-attachments/assets/8da107ff-3e31-4b0e-a54d-9cbe91d9d1f0" />

 Now in MLOps level one, the goal is to perform continuous training of the model by automating the ML pipeline. 

This lets you achieve continuous delivery of model prediction service. Note that I'm saying that continuous delivery of model prediction service only, and not the whole ML application, which acts upon the model inferences.

To characterize it, silos are broken in this level. At level one of maturity, 

1. **People** : data scientists work directly with data engineers to convert experimentation code into reputable scripts or jobs. Vice versa to it, data engineers also work with data scientists and software engineers to manage inputs and outputs. Software engineers in turn, would be working with data engineers to automate model integration into application code.
2. **data gathering** data at this level is moved into modern searchable data stores. Corporate databases are used with shared file storage and you create some pipelines for data gathering, data analysis, data preparation, and they all are automated.
3. **Development phase** is also automated. All those manual steps of experimentation are now converted into an orchestrated experiment. The good thing which you achieve in this level is the modularized code. Your code is no longer in a single notebook. A single notebook was never reusable, but to construct ML pipelines components need to be reusable, composable, and potentially shareable across ML pipelines. And hence, in MLOps level one, the source code for those components are modularized.
4. **model release** As organization begin to mature, they slowly start automating the delivery process. They start scripting the actions that DevOps people used to perform manually. Now, based on the model release strategy,
5. Then no continuous integration till MLOps level one.
6. **model deployment** rather than deploying a train model as prediction service in production every time, in MLOps level one we put a whole training pipeline itself, which automatically and recurrently runs to serve the train model as a prediction service in production environment.In this way, we are implementing the continuous training of model in production. When the whole training pipeline is deployed, the model is automatically trained in production using fresh data. But note that deployment is still not fully automated. It is sort of semi manual-efforts you can say.
7. **Application integration, unit and integration tests** are put in place for each model release. This process is comparatively less reliant on data scientist expertise than in previous level.
8. **Monitoring** You start doing active monitoring at this stage with some complex tools. And triggers are also put in place, which can retrain the model in production.

<img width="613" height="385" alt="image" src="https://github.com/user-attachments/assets/cfcf6095-4b5c-41ad-893f-242b06dcafa6" />

  if you go see workflow digram,  experimentation part is automated. Deployment is semi-automated. And in addition to it, an optional component for level one MLOps pipeline is **feature store**. A feature store is centralized repository where you can standardize the definition, storage and access of features for training and serving. The feature store helps the data scientists to discover and to reuse the available feature sets for their entities instead of recreating the similar ones. This feature store is used as a data source in experimentation, continuous training and serving. Using the feature store in all those three phases makes sure that features used for training are the same ones used during serving.

one more component of **ML metadata store** is put in place. This repository is to keep the information about each execution of the ML pipeline. Information like which pipeline version and component versions were executed in a run, the start date, end date, and how long the pipeline took to complete each of the steps in it, the executor of the pipeline, the parameter arguments that were passed to the pipeline, then, the model evaluation metrics produced during the model evaluation step to compare the performance of newly trained model with the performance of current model running. So everything regarding a pipeline run is stored in this ML metadata store.
This metadata repository will help us with the data and artifacts lineage, reproducibility, and comparisons. With this, our MLOps level one is done,

let's jump on to the next supreme level of automation.

## MLOPS level 2
<img width="455" height="362" alt="image" src="https://github.com/user-attachments/assets/42f103e7-dc1a-437c-bc84-4ea9395ee285" />


Even when most of the things are put in place in level one there is still room for improvement. 

ML Ops 2 is the highest level of automation achieved in ML Ops and the last goal post for any good ML platform. This implementation is so powerful that by just doing a comment in the code can trigger a set of 
numerous automated activities and let your pipeline deploy in production.

1. data obviously you have proper datalakes and target data warehouses automated pipelines for data gathering, data analysis. But along with that what you have strict comprehensive data governance secure APIs for database accesses and role-based access controls at user and group level.
2. **continuous integration and continuous deployment** Continuous integration allows to automate the unit testing building and packaging phase. while the deployment which was semi-automated in ML Ops Level 1 is fully automated here.
3. **Continuous Deployment** Talking about deployment now guys, as the ML projects begin to scale creating and maintaining a growing collection of scripts for automation is not worth the time. So you look out for a more manageable solution. At this level we start offloading jobs to a deployment platform which is nothing but a continuous deployment pipeline.
4. Application code itself would have the unit and integration test for each model release.

## Importance Maturity levels

The purpose of this maturity model is to help clarify the MLOps principles and practices. The maturity model shows the continuous improvement in the creation and operation of a machine learning application environment.
it is a way show the roadmap of MLOps capability in your project. These levels are series of milestones that can guide you in how to grow your MLOps capability in increments, rather than overwhelming the team for a fully mature environment.

we can use it as a metric for establishing the progressive requirements needed to measure the maturity of a machine learning production environment and its associated processes.

These levels can be used for estimating the scope of the work for new engagements, then establish realistic success criteria then identifying the deliverables

