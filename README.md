# Apply Terraform | Create Buildspec File | Create Build Project in CodeBuild

Create buildspec.yaml to run cicd pipeline

version: 0.2

phases:
  install:
    runtime-versions:
      python: 3.x

  pre_build:
    commands:
      - cd cicd # change directory
      - chmod +x install-terraform.sh configure-named-profile.sh apply-terraform.sh # make files executable
      - ./install-terraform.sh # install terraform
      - ./configure-named-profile.sh # configure named profile

  build:
    commands:
      - ./apply-terraform.sh
