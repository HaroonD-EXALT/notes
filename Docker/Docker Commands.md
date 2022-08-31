* docker ps => print current running containers 

* docker run Image_Name => run image 

* docker run **-p pcPort:dockerPort** Image_Name => run image container on port 3000 in my pc (Expose the port)
  
*   docker run -p pcPort:dockerPort **-d** Image_Name => sperate docker from terminal (detach)

* docker run -p pcPort:dockerPort -d --name ContainerNameImage_Name => run new container with specific name  for the container 
  
* docker stop Image_Id/Image_name
* docker kill Image_Id/Image_name
* docker exec -it container_name => run command inside the container 



