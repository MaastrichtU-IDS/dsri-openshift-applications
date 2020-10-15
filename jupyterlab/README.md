Build custom JupyterLab image for OpenShift

```bash
docker build -t ghcr.io/maastrichtu-ids/jupyterlab-on-openshift:sparql .
```

Using a specific Dockerfile:

```bash
docker build -f Dockerfile -t ghcr.io/maastrichtu-ids/jupyterlab-on-openshift:sparql .
```

Test run:

```bash
docker run --rm -it --user $(id -u) -p 8888:8888 -e VIRTUAL_HOST=jup.137.120.31.102.nip.io -e JUPYTER_TOKEN=password -v $(pwd):/home/jovyan ghcr.io/maastrichtu-ids/jupyterlab-on-openshift:sparql
```