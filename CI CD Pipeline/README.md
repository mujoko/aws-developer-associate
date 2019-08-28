# CI/CD
Continuous Integration, Continuous Delivery and Continuous Deployment.
## CodeCommit
It is git repo manage by AWS
## CodeBuild
Build spec files must be expressed in YAML format.
```
version: 0.2

run-as: Linux-user-name

env:
  variables:
    key: "value"
    key: "value"
  parameter-store:
    key: "value"
    key: "value"
  git-credential-helper: yes
            
phases:
  install:
    run-as: Linux-user-name
    runtime-versions:
      runtime: version
      runtime: version
    commands:
      - command
      - command
    finally:
      - command
      - command
  pre_build:
    run-as: Linux-user-name
    commands:
      - command
      - command
    finally:
      - command
      - command
  build:
    run-as: Linux-user-name
    commands:
      - command
      - command
    finally:
      - command
      - command
  post_build:
    run-as: Linux-user-name
    commands:
      - command
      - command
    finally:
      - command
      - command
artifacts:
  files:
    - location
    - location
  name: artifact-name
  discard-paths: yes
  base-directory: location
  secondary-artifacts:
    artifactIdentifier:
      files:
        - location
        - location
      name: secondary-artifact-name
      discard-paths: yes
      base-directory: location
    artifactIdentifier:
      files:
        - location
        - location
      discard-paths: yes
      base-directory: location
cache:
  paths:
    - path
    - path
```
## CodeDeploy
The lifecycle  for EC2
![See the Deployment strategy](EC2Hook.PNG)

The lifecycle-event for ECS
![See the event](lifecycle-event-order-ecs.png)

## Tips


