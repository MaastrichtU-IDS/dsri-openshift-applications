

Template to deploy on DSRI in `template-data-stewardship-wizard.yml`

RabbitMQ have issues on OKD4, but all other services works when running with `anyuid`

Check the project `data-stewardship-wizard`

The proper way to deploy RabbitMQ would be: https://www.rabbitmq.com/kubernetes/operator/install-operator.html

> See also: old docs to deploy rabbitmq on OpenShift: https://stackoverflow.com/questions/45569931/how-to-correctly-setup-rabbitmq-on-openshift

Data Wizard server require a config file, use a ConfigMap:

```
"Config load failed"
"Server can't load 'engine-wizard/config/application.yml'. Maybe the file is missing or not well-formatted"
GeneralServerError "AesonException \"Error in $.general.serviceToken: expected String, but encountered Null\""
```
