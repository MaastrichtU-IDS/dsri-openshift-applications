

Templates and example build for the DSRI OpenShift applications.

## Upload templates to your project

### Data science templates

Running as non root, without sudo privileges

```bash
for template in $( ls templates-datascience/*.yml ); do oc apply -f ${template} ; done
```

### Anyuid templates

Containers running as root user.

GPU templates and templates in anyuid folder require the `anyuid` service account enabled in your project (to run the container as root user).

> [Contact us to request](https://maastrichtu-ids.github.io/dsri-documentation/help) `anyuid` privileges if necessary

```bash
for template in $( ls templates-anyuid/*.yml ); do oc apply -f ${template} ; done
```

### GPU templates

Containers running as root user

```bash
for template in $( ls templates-gpu/*/*.yml ); do oc apply -f ${template} ; done
```

## Create custom Docker image

For JupyterLab or VSCode server: check their respective folders.

## Create app from template using command

Create app from template file using the CLI:

```bash
oc new-app -f templates-datascience/template-jupyterlab-dynamic.yml -p APPLICATION_NAME=jupyterlab-dynamic,PASSWORD=PASSWORD
```

Create app from existing template in your DSRI project using the CLI:

```bash
oc new-app jupyterlab-dynamic -p APPLICATION_NAME=jupyterlab-dynamic,PASSWORD=PASSWORD
```

Delete your application:

```bash
oc delete all --selector app=jupyterlab-dynamic
```

> Replace `jupyterlab-dynamic` by your **APPLICATION_NAME**

Delete all applications from a template:

```bash
oc delete all,secret,configmaps,serviceaccount,rolebinding --selector template=jupyterlab-dynamic
```

## Useful links

[Browse the list of Icons](https://rawgit.com/openshift/openshift-logos-icon/master/demo.html) for Templates in the Catalog.

Convert JSON to YAML: https://www.json2yaml.com

**See also**:

* [OpenShift documentation to generate Template](https://docs.openshift.com/container-platform/3.11/dev_guide/templates.html#export-as-template) from deployed service
* Deployment from Jupyter

  * https://github.com/jupyter/docker-stacks/tree/master/examples/source-to-image 

  * See [their template](https://raw.githubusercontent.com/jupyter/docker-stacks/master/examples/source-to-image/templates.json)