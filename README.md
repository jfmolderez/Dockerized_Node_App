## Usage :
- Build an image from the docker file: `docker build .` and get the `image_id`  from the output
- Create a container in attached mode : `docker run -p 8000:80 image_id` 
- Alternatively, create the container in detached mode : `docker run -d -p 8000:80 image_id` 
- Check that the container is running and get the `container_name` : `docker ps`
- Check that the container is effectively running with the browser at `localhost:8000`
- Stop the container : `docker stop container_name`
- Start again the container in detached mode by default : `docker start container_name`
- Possibly, check the logs: `docker logs container_name` or if you want also to attach : `docker logs -f container_name` 
- Stop the container : `docker stop container_name`