# CircleCI Orb for Executing VMware Code Stream (SaaS) Pipelines 

CircleCI Orbs provide an easy way to execute integration tasks as a part of the CI/CD process that CircleCI executes. 
This Orb specifically executes a Code Stream pipeline by ID. The pipeline has 2 required inputs: 
* CSP Refresh Token 
* Pipeline ID 

These values can be included as local environment variables or as project level environment variables within CircleCI. 

# Consuming this Orb 

This orb should be included in your ```.circleci/config.yml``` file. You can see an example of leveraging this capability here: 

```
version: 2.1

orbs:
    vmwarecs: vmware/codestream@1.0.0


workflows:
  Code-Stream-Execute:
    jobs:
      - vmwarecs/callcs:
            requires: 
                - docker/publish
            csp_token: CSP_REFRESH_TOKEN
            pipeline_id: PIPELINE_ID
```
