Build custom VisualStudio Code server image for DSRI. Based on https://github.com/cdr/code-server

Additionally installed: Python3, yarn, PHP and Fortran

Build:

```bash
docker build -t ghcr.io/maastrichtu-ids/code-server:latest .
```

Push:

```bash
docker push ghcr.io/maastrichtu-ids/code-server:latest
```

Test run:

```bash
docker run --rm -it -p 8080:8080 -e PASSWORD=password -v $(pwd):/home/coder ghcr.io/maastrichtu-ids/code-server:latest
```

