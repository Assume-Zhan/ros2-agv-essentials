# ROS2 Cartographer

### Run with docker

```bash
git clone https://github.com/j3soon/ros2-agv-essentials.git
```

```bash
cd ros2-agv-essentials/cartographer_ws/docker
docker-compose pull
docker-compose up -d --build
```

### Simple Test With Turtlebot3

- Attach to the container

  ```sh
  docker attach ros2-cartographer-ws
  cd /home/ros2-agv-essentials/cartographer_ws
  ```
- Open the turtlebot simulation in `tmux`

  ```bash
  export TURTLEBOT3_MODEL=burger
  ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py
  ```
- Run the SLAM node in new window of `tmux`

  ```bash
  ros2 launch turtlebot3_cartographer cartographer.launch.py use_sim_time:=True
  ```
- Run the control tool in new window of `tmux`

  ```bash
  rqt_robot_steering
  ```

#### References

- [Cartographer Demo]()