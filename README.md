# The_DevSecOps_Series_HandsOn_Practice_Projects
DevSecops Training


    name: "Pipeline"
    trigger:
      branches:
        include:
        - main
    pr:
      branches:
        include:
        - master
    on:
      workflow_dispatch:

    jobs:
      semgrep:
        runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - uses: returntocorp/semgrep-action@v1
        with:
          config: "p/default" 
