# MLOPS
A culture with set of principles, guidelines defined in a machine learning world to seamlessly integrate/automate the development phase with the operational phase

<img width="263" height="224" alt="image" src="https://github.com/user-attachments/assets/1aca34b1-1840-4877-bc8b-a903c433698c" />

## Define Standards / Principles

1. Transition friction:
   - Use notebooks templates that define common functionality e.g database connection template, fetching data etc
   - Proper documentation

2. Version control system:
   - Version control for code, data, environments and artifacts
3. Performance:
   - leverage distributed computing and containerization tools, e.g Docker , kubernetes

4. Automation
   - build workflows CI/Cd pipelines
   - MLOPS is pipelines centric, Put pipelines in production than putting a model
5. Monitoring
   - Powerful innovative monitoring tools to monitor data, features, distribution, latency, uptime, memort utilization etc
   - Monitoring tools, e.g Prometheus, grafana
6. Continuous Training
   - Automated retraining of models based on triggers or regular frequesncy

<img width="682" height="387" alt="image" src="https://github.com/user-attachments/assets/cf6893da-efca-481a-b5a2-fd3fb2fb865e" />

----------------
<img width="607" height="197" alt="image" src="https://github.com/user-attachments/assets/642d0f28-9da3-43a0-a958-3141d645351e" />


## Benefits from MLOPS

- creating a shared language among the extended team
- a lot of automation

**Data Scientists** can now focus more on research and experimentation while having the overall visibility of their deployed models

**ML engineers** get less resistance from understanding the experiments, reproducibility is not longer a problem

**Application developers** do not need to change the code every time, the model is changed, Model and application are decouples from each other

**Risk and compliance team** get benefitted as MLOPS infrastructure allows to streamline the internal processes since complete lineage is maintained so auditing process is smooth
**clients** can make better busines decisions when they always have the updated model giving predictions 


## Difference between MLOPS and DEVOPS
| Aspect | DevOps | MLOps |
|------|--------|-------|
| Team Composition | Team comprises DevOps engineers | Diverse team including Data Scientists, ML Engineers, Data Engineers, and DevOps engineers |
| Development Cycle | Linear development cycle | Iterative development cycle |
| Versioning | Versioning of only code | Versioning of code, data, features, environments, etc. |
| Compute Requirements | Projects are not compute intensive | Projects are compute intensive |
| Continuous Integration (CI) | CI focuses on testing and validating code | CI focuses on testing and validating both code and data |
| Continuous Delivery / Deployment (CD) | CD focuses on deploying a service | CD focuses on deploying multiple pipelines |
| Monitoring | Monitor throughput, latency, CPU utilization, etc. | Monitor model performance, data drift, latency, throughput, and resource utilization |
| CICD | Devops is continuous integrations and coninuous deployment | MLOPS is continuous integration, continuous deployment and continuous training |
