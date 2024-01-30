

**MAKE SURE TO CHECK THE AUTOGEN GITHUB FOR CHANGES, AS THESE INSTRUCTIONS WILL LIKELY NOT BE VALID FOR LONG** 

The date is 24/01/2024.

1. git clone https://github.com/microsoft/autogen.git

2. cd autogen/.devcontainer

3. Run:

```shell
docker build -f dev/Dockerfile -t autogen_dev_img .
```    

**(Make sure to include the ' . ')**

4. Run:

```shell
docker run -it -v $(pwd)/autogen:/app autogen_dev_img
```

5. You should now be in the docker container. A few setup points and notes:

```notes

1. From the terminal inside docker run

sudo python setup.py build && sudo python setup.py install. 

This setup.py file is in the root of the autogen directory.

4. If you install the docker extension for vscode you will be able to connect to the container. In the docker extension tab in vscode right click the container in the containers submenu and click 'connect to vscode', this will open another vscode window where you can create files and folders inside the container.

5. Important note. Any scripts must be run from the terminal either in vscode or in the terminal you connected to docker with. If you use the python button in the top right the autogen scripts WILL NOT WORK. Don't waste time trying to fix 'flaml' dependencies.

4.To exit the container type 'exit' in the terminal

5.Then 'docker stop {container name}'. (to find the name either look at the container name in docker desktop or run 'docker container ls' from the host system)
```

You now have a persistent docker volume. To restart it run:

```shell
docker start {container_name} 
```

again you can find this with 'docker container ls' or check in docker desktop. Additionally you make have to start docker again if you have restarted your system. Opening docker desktop will usually solve this problem. On linux you can run:

```sudo systemctl start docker```

To access the container run:

```sudo docker exec -it {container name} bash```


**These instructions especially those at the beginning and end may need to be slightly adapted for Windows and MacOS environments.**


