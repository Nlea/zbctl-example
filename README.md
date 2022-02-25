# zbctl-example
This repo contains a bpmn diagramm with set properties for [Camunda Cloud](https://docs.camunda.io/). It contains a shell script to create a worker using [the CLI client zbctl](https://docs.camunda.io/docs/apis-clients/cli-client/) for Camunda Cloud. 

## Prerequirements
- [Camunda Cloud Account](https://docs.camunda.io/docs/guides/getting-started/)
- [Create client connection credentials](https://docs.camunda.io/docs/guides/getting-started/setup-client-connection-credentials/)

## Install zbctl client
The client is available via:
-[npm](https://www.npmjs.com/package/zbctl)
-[snap](https://snapcraft.io/zbctl)
-[homebrew](https://formulae.brew.sh/formula/zbctl)


## Set enviroment variables
Set the connection credentials as enviroment variables in your Terminal. You can test the setup with the command: 
```
zbctl status
```


## Start a process instances with Variables
```
zbctl create instance Process_chooseActivity --variables "{\"toDo\":\"random activity\", \"weekday\":\"Monday\"}"
```

## Create a Worker
Use the shellscript from the repo to provide the execution logic for the zbctl handler. Download the shellscript and make it executable with the ```chmod``` command

```
zbctl create worker randomActivity --handler "./randomActivityWorker.txt"
```



