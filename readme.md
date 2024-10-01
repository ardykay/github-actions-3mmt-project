# Basic pipeline with automated build and test stages using github action.

## Introduction
Github Actions is a CI/CD tool that allows you to automate your workflow. It is a powerful tool that can be used to build, test, package, release, and deploy your code. In this guide i will create a Github Actions workflow.

## Prerequisites
- Github account
- Repository with code (you can use this repository)

## Steps
1. Go to your Github repo that contain the project
  ![1](https://github.com/user-attachments/assets/2b78c4c7-d192-4059-94b4-0689dd33f13a)

2. Go to the action tab on the top. 
  ![2](https://github.com/user-attachments/assets/f1e2dc1b-2cc0-48aa-82b8-2224cab8f0f1)

3. Define the workflow
```yml
    name: Basic pipeline with automated build and test stages Project

on:
  pull_request:
    branches: [ "main" ]
  push:
    branches:
      - main 

jobs:
  test:
    runs-on: ubuntu-latest
    container:
      image: node:20
    steps:
      - uses: actions/checkout@v3
        with:
          node-version: 20
      - run: npm ci
      - run: npm test
      - run: npm run build
```
   ![3 NEW ORIG](https://github.com/user-attachments/assets/0965fd7d-19ad-4ed8-aec5-28ba2ee9ac44)

5. Commit your change a workflow/pipeline is created which will trigger when there is a push or pull in this project repository
  ![5](https://github.com/user-attachments/assets/ff1d170e-45a2-49ba-a6ce-4ab327453bd1)

6. Check the Actions tab in the repository to view 
  ![6](https://github.com/user-attachments/assets/aaa75c46-1fcf-4b7b-b9da-1bb6057a8092)

  **Summary of workflow**
  ![ss](https://github.com/user-attachments/assets/e2bc0b92-08cd-4f7c-a5ba-824faf20f073)
  Click on it to learn more about the job
  ![our job success](https://github.com/user-attachments/assets/1dfaf56f-adff-4c20-9c76-607bbf4813d6)

  I have succesfully created a CI pipeline with automated build and test



