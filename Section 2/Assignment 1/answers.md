1.

Navigate to the directory of each application and execute the following command:

```bash
docker build .
```

2.

We have the image identifiers from the building step (before).

For the node application, we execute the following command:

```bash
docker run --rm -p 3000:3000 -d <node_image_id>
```

For the python application, we execute the following command:

```bash
docker run --rm -i <python_image_id>
```

3.

For the node application, we execute the following command:

```bash
docker run --rm -p 3000:3000 -d --name node_app <node_image_id>
```

For the python application, we execute the following command:

```bash
docker run --rm --name python_app -i <python_image_id>
```

4.

To stop the node app's container, execute the following command:

```bash
docker stop node_app
```

Respectively, for the python application, execute the following command:

```bash
docker stop python_app
```

For the other node container that is still running, it depends on the automatically assigned
name from the docker daemon.

Alternatively, we could execute the following command that stops every running container:

```bash
docker stop $(docker ps -aq)
```

5.


For the node application, execute the following build command:

```bash
docker build -t node-app .
```

For the python application, execute the following build command:

```bash
docker build -t python-app .
```

6.

```bash
docker run --rm -p 3000:3000 -d --name node_app_container node-app
```

For the python application, we execute the following command:

```bash
docker run --rm --name python_app_container -i python-app
```