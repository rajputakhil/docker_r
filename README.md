# docker_r

## Running RStudio Server ##

1. Install docker from the following URL

https://docs.docker.com/v17.09/engine/installation/linux/docker-ce/ubuntu/#install-docker-ce-1

2. Pull the Docker image

    sudo docker pull rocker/rstudio

Verify

    sudo docker images

3. From the docker window, run:

```s
sudo docker run -d -p 8787:8787 -v $(pwd):/workspace -e PASSWORD=Sniggdha13 --name rstudio rocker/rstudio
# replace <password> with a password of your choice
# Folder sharing: To share files and folders between your ```docker``` image and your host OS you can use the ```-v``` option. This acts much like running ```RStudio``` in the working directory.
```

That will take a while to download.

Linux users might want to add their user to the docker group to avoid having to use ```sudo```. To do so, just run ```sudo usermod -a -G docker <username>```. You may need to login again to refresh your group membership. (Mac and Windows users do not need to use sudo.)

4. Once the download is finished RStudio-Server will launch invisibly. To connect to it, open a browser and enter in http://localhost:8787, and you should be greeted by the RStudio welcome screen. Log in using:

* username: rstudio
* password: <password>

and you should be able to work with RStudio in your browser in much the same way as you would on your desktop.

## Folder sharing

To share files and folders between your ```docker``` image and your host OS you can use the ```-v``` option. This acts much like running ```RStudio``` in the working directory.