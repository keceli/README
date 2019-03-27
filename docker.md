# How to use Docker containers?

Build the image with
```
docker build -t <MYIMAGE> .
```
General convention for <MYIMAGE> is username/imagename, i.e
keceli/petsc
Run with
```
docker run -it <MYIMAGE> bash
```

Change tag
```
docker tag <MYIMAGE> <NEWIMAGE>
```


To push the image to docker hub:

```
docker login
```

Then

```
docker push <NEWIMAGE> 
```
To run a Jupyter notebook within the container, start the container with:
```
docker run -it -p 8888:8888 keceli/pacc bash
```
Within the container, run:
```
jupyter notebook --ip 0.0.0.0 --allow-root
```


