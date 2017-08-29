## To start container

xhost +local:root;  sudo nvidia-docker run -ti -e masteruri=localhost --network=host --rm --device=/dev/video1:/dev/video1 --privileged eyerissfd:latest

## Add rosbridge and start

```
apt-get update && apt-get install -y ros-indigo-rosbridge-suite ros-indigo-web-video-server

rosrun rosbridge_server rosbridge_websocket
rosrun web_video_server web_video_server

roslaunch eyeris eyeris_usb_cam_node.launch &
```

# How to get docker image cmd

```
sudo docker inspect  -f "{{.Config.Cmd}}"
```
