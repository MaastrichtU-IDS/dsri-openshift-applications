Build custom VisualStudio Code server image for OpenShift with PHP installed:

```bash
docker build -t ghcr.io/maastrichtu-ids/jupyterlab-on-openshift:vscode .
```

Test run:

```bash
docker run --rm -it -p 8888:8888 -e PASSWORD=password -v $(pwd):/home/coder ghcr.io/maastrichtu-ids/jupyterlab-on-openshift:vscode
```