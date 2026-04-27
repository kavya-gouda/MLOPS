# MLOPS Stack requirements

Before starting tool names, let us first discuss about what are type of tools we should be needing. This is more like what are features an MLOps platform should provide or you should look out for while choosing an MLOps platform. Also, as a takeaway, we can see that if at all you are planning to create your own MLOps platform, you would be needing those type of features and tools. Now, if we compress the whole MLOps life cycle, it can be seen in three stages:
1. data gathering
2.  modeling
3.  deployment.
4.  
<img width="636" height="268" alt="image" src="https://github.com/user-attachments/assets/ecdfa107-c688-475b-8e94-59096f98d990" />

Each phase is comprised of multiple steps and tasks, so different tools will be used in different phase.

<img width="685" height="328" alt="image" src="https://github.com/user-attachments/assets/e8926072-0045-4f5b-a225-3b99a7d163fa" />


1. **data gathering and preparation** :You can no longer do manual scraping of data or dealing with just flat or some Excel files.Your platform should be able to gather batch as well as streaming data. To automate this process, you have to build pipelines that would ingest any batch of streaming data, do the cleaning transformation stuff on it, and have it prepared for the model to feed. You also might need some visualization tools here for initial exploratory data analysis.

2. **source control** for versioning the code data ML model artifacts and so. Reproducibility was one major issue which MLOps addresses. So, a good MLOps platform should be built with reproducibility as a first-class citizen. 

3. **research and experimentation** Platform should be data scientist friendly, means it should work out of the box with popular ML frameworks so that the innovation is not hindered by restricting your data science teams 
to work only on specific tools and frameworks. platform should support PyTorch, Keras, TensorFlow, PsycLearn, Catalyst. The platform should host various notebooks for development, which should enable data scientists to perform rapid experimentation while keeping a track of all the result metrics of the experiments.

4. **Hyper parameter tuning**  Choosing the correct hyper parameters for machine learning or deep learning models is one of the best ways to extract the last use out of our models.

5. **Distributed model training**  MLOps platform should be able to automatically train the model using different sets of data. We know that training a model is resource extensive and may require GPUs for days or weeks.
   the platform should provide services that can scale itself and also can do distributed model training.
6. **AUTO ML** To save you from the outdated rounds of model training with different permutations and combinations of algorithm data features, the platform should have AutoML.
7. **deployment** Deploying models for inference is not a trivial task. It requires a lot of activities to be performed. example, it requires collecting the various model artifacts, setting up a service stack, exposing an endpoint, emitting real-time metrics,  Now, obviously, for all these tasks, automated deployment is what you will be looking for,but more importantly, is using the container services like Docker or Kubernetes to allow for auto scaling of the models.
8. **model registry service** A model registry is a centralized repo for hosting all the important artifacts for production-ready models. While some MLOps platforms provides ready-to-use model registries, others provide you with a toolkit for assembling of one. At the very least, a concrete model registry needs to include training data, including model type, key artifacts, features, and creation time, training parameters and hyper parameters associated with the current version, and key performance metrics like accuracy, precision, recall. registry should be able to store any extra data that you need to effectively deploy the model in runtime.
9. **Feature vector storage** One of the critical components in machine learning project is feature engineering, which can be shared and reused between teams and projects. If you are from machine learning background, you would know that ML features are measurable properties of phenomena under observation, like raw words, pixels, sensor values, fields in a CSV file. Having a feature store in place facilitates collaboration between teams. It reduces duplication by reusing the features, which in turn, reduces the feature engineering cost per model, and since the features would be getting reused, so it also increases the productivity of ML engineers as they would spend more time on models than creating feature-serving APIs.
10. **monitoring** Your tool should provide you with a real-time performance view of the deployed models. It should have some alerts mechanism, which can alert a person or trigger a retraining of model upon seeing the data drift or division in the performance of model.
11. **governance** It is good if the platform is providing model governance services to control access, implement policy, and tracks activity for models. The platform should give the capability to track the end-to-end trail of all of your ML assets by using the metadata. Using the ML metadata store at any point of time, you should be able to explain your models, meet the regulatory compliance, and understand how models arrive at a result for given input.
12. **compliance and audit services** In most regulated industries, there can be an additional compliance and audit stage where models are reviewed by internal auditors or even external auditors. it becomes mandatory in models where risk is involved, such as models that manage financial outcomes. Since these models have direct impact on the financial values, it is extremely important to detect and correct any biased or unethical outcomes. So, auditing the inferences with a service would be a great add-on.

when deployment is done on some model servers that allow you to stand up and serve any model you train as a real-time HTTPS endpoints.

Now in turn, the things to look out for model servers are fallback support. As you deploy a new model into production,you might find that performance drops drastically. The ability to have a different model, maybe a previous version or a very simple model during these periods of degraded performance,can be very helpful. 

The scaling capacity at ease of scaling out is always. Canary A/B framework to roll out the deployment for a small subset of users. Then just in case, if you have multiple models where output of one model is input to the other, then the model servers should be supportive to co-locate multiple models in the same server, or at least an easy connection between the models. security is extremely important. These are some of the basic things that model servers should provide to help with the MLOps culture, and rest would be as-per-need basis.


## Platform Maturity comparison

Multiple players are diving into creating their own mlops platform. The cloud providers are building new services and streamlining the already built services to achieve mlops. clouds like Azure AWS, google have services of Azure Machine Learning, Auto ml, Azure DevOps, Amazon Sales Maker, and Google AI respectively.

While cloud providers are leveraging and integrating the open source tools to build their own MLOPS platform. And each of them are at its own level of development. none is fully mature. if we list down the few and try to compare them broadly the comparison can be done for four key stages of MLOPS.

Data gathering and transformation, model building,

experimenting, training, tuning, testing, deployment.

And the last one, monitoring, auditing

management and retraining.

And these are the few

of the platforms I'm doing comparison on.

Note that these are not the best picks

or the ones I recommend.

I just chose them for the comparison.

The dots here represent the facility they provide

and the color represents the maturity level of it.

Darker the color, more majorities.

Now some are focused to build their product

from the data gathering phase and other choose to

build the deployment and monitoring phase first.

You can take a screenshot of this diagram

as it'll be helpful for you at times.

And please note that this is the situation as of today.

In future, it may change as the teams are progressing.

So please keep yourself updated.

So from this picture, we can see Pachyderm is a pioneer

in data wrangling.

Pachyderm delivers version control

for data using language agnostic data pipelines.

Basically it is a gate for your data.

It doesn't just version the data, it manages the

transformations tool.

This gives a clear data lineage.

It tracks all those data

revisions and the associated transformations.

So you can say it very well, handles the reproducibility

requirements, but at the same times it also

lacks the monitoring facility totally and offers very less

in terms of model building and training.

Pachyderm is available in three versions, Community edition

which is an open source with ability to be used anywhere.

Then Enterprise Edition, a complete version

controlled platform.

Last is hub addition, which is still in a better version

and it combines the characteristics of

both the previous versions.

Next is Algorithmia, which can deploy, manage

and scale your machine learning portfolio.

Depending on which plan you choose, algorithmia can run

on its own cloud, on your premises, on VMware or

on a public cloud.

It can maintain models in its own depository or

on GitHub.

This platform automates ML deployment

provides maximum tooling Flexibility,

optimizes the collaborations

between operations and development

by leveraging the existing SDLC and CSC D practices.

Basically, Algorithmia is more

into providing you easy and hassle-free deployment services

but it lacks data gathering and does not support SAS.

ML Flow is an open source machine learning life

cycle management platform

from Data Bricks AM Flow covers three components

modeling, deployment, and monitoring.

All of which are in early stages as of now.

But the project is promising.

The tool is library agnostic

so you can use it with any machine learning library

and in any programming language.

This platform is very suitable

for individuals and for teams of any size.

Next Kubeflow.

Kubeflow is also in the emerging list of MLS platforms.

Kubeflow, you can see as a ML tool kit for [Inaudible].

It is a perfect platform for Kubernetes users.

Build on [Inaudible] and Google's internal ML pipelines.

Kubeflow is a system for deploying, scaling

and managing complex systems.

It offers several components that you can use to

build your ML training, hyper parameter tuning

and serving workloads across multiple platforms.

But all of this

in the initial early stage.

Guys, apart from this

there are many players in the market like Polyaxon,

Valohai, Allegro, seldom Terminals db,

Superb ai, tacton, et cetera.

Each of them will fall in any of the blocks here.

Valohai and Allegro have their prints

in each of the category with their own maturity levels.

Now, comparing each of them

in detail is a totally different topic of discussion.
