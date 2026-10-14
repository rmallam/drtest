# drtest

Node.js golden-path service with Jenkins, Helm, and Sonar

## Pipeline

Jenkinsfile stages: **Install → Lint → Unit tests → SonarQube → Helm lint**.

Point a Jenkins job named `demo/drtest` at this repo. Set credential `SONAR_TOKEN` to run the scanner against `http://sonarqube.sonarqube.svc:9000`.

## Deploy

```bash
helm upgrade --install drtest chart -n demo-dev
```

The chart labels pods `backstage.io/kubernetes-id=drtest` for Topology.

## Dev Spaces

https://devspaces.devspaces.ocp.dkccw.sandbox3257.opentlc.com#https://github.com/rmallam/drtest?new&devfilePath=devfile.yaml
