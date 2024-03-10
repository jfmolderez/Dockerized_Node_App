## Usage :
- Build an image from the docker file: `docker build .` and get the `image_id`  from the output
- You can also assign a name and a tag to the image: `docker build -t goals:latest .`
- Optionally, check the presence of the image : `docker images`
- Create a container in attached mode : `docker run -p 8000:80 image_id` 
- Alternatively, create the container in detached mode and name it: `docker run -d -p 8000:80 --name goalsapp goals:latest`  
- Alternatively, remvoe the container automatically whenever we stop it : `docker run -d --rm -p 8000:80 --name goalsapp image_id` 
- Check that the container is running and get the `container_name` : `docker ps`
- Check that the container is effectively running with the browser at `localhost:8000`
- Stop the container : `docker stop container_name`
- Start again the container in detached mode by default : `docker start container_name`
- Possibly, check the logs: `docker logs container_name` or if you want also to attach : `docker logs -f container_name` 
- Stop the container : `docker stop container_name`
- Optionally, delete the image : `docker rmi image_id`

## Additional remarks
The names of the images have two parts : the name itself and the tag separated by a colom. The name is for a group of images and the tag corresponds to the specific image, its specialization.

`RUN` is an image build step, the state of the container after a `RUN` command will be committed to the container image. A dockerfile can have many `RUN` steps that layer on top of
one another to build the image.

`CMD` is the command the container executes by default when you launch the built image ,i.e. a new container. A dockerfile will only use the final `CMD` defined. 