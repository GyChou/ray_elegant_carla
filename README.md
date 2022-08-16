# mcppoElegantRLforCarla
There is the implementation of multi-constraint proximal policy optimization (MCPPO), which is modified based on a DRL framework -- [ElegantRL](https://github.com/AI4Finance-Foundation/ElegantRL)(小雅). The carla environment is modified based on [gym-carla](https://github.com/cjy1992/gym-carla). Please refer to our paper for details.

![Image text](https://github.com/GyChou/mcppoElegantRLforCarla/blob/main/images/town07-part.gif)

## Get started

### OS and Carla

Our experimental environment is based on Ubuntu18.04 and Carla0.9.11
Before training in Carla, you need
- install Carla, the tutorial: https://carla.readthedocs.io/en/latest/start_quickstart/
- install Docker, the tutorial: https://docs.docker.com/engine/install/ubuntu/
- install Nvidia-docker2 (for running env by GPU), the tutorial: https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker
- start carla server, the tutorial: https://carla.readthedocs.io/en/latest/build_docker/#nvidia-docker2 or start with ```python ./gym_carla_feature/start_env/demo/startServer.py```

### Python environment
Please see requirements.txt
```
pip install -r requirements.txt
```
You can run PID control to test 
```
python gym_carla_feature/start_env/demo/rule_demo.py
```
to test if carla is installed correctly.
### Training

After runing carla server, you can start a training with a quickstart shell
```
bash ./start/carla_veh_control_run.sh
```
, which includes PPO, MCPPO, SAC, D3QN. Or start with 
```
python gym_carla_feature/start_env/demo/veh_control.py
```
You also use ray_elegantrl to try other envs such as
```
python ray_elegantrl/demo.py
```
### Evaluation
The tensorboard file and model file will be saved in ```./veh_control_logs```

### Test
The policy our trained is in ```./veh_control_logs/veh_control/town07-V1```.

Run PID drive policy by 
```
python gym_carla_feature/start_env/demo/rule_demo.py
```
Run DRL drive policy by 
```
python gym_carla_feature/start_env/demo/eval_policy_carla.py
```
## Citation
@inproceedings{zou2022mcppo,
  author    = {Guangyuan Zou and
               Ying He and
               F. Richard Yu and
               Longquan Chen and
               Weike Pan and
               Zhong Ming},
  title     = {Multi-Constraint Deep Reinforcement Learning for Smooth Action Control},
  booktitle = {Proceedings of the Thirty-First International Joint Conference on
               Artificial Intelligence, {IJCAI} 2022, Vienna, Austria, 23-29 July
               2022},
  pages     = {3802--3808},
  publisher = {ijcai.org},
  year      = {2022},
  url       = {https://doi.org/10.24963/ijcai.2022/528},
  doi       = {10.24963/ijcai.2022/528}
}
<!-- The arxiv link to the paper:  -->


## Thanks 
Thanks for [小雅](https://github.com/AI4Finance-Foundation/ElegantRL) and [Yinyan Zeng](https://github.com/Yonv1943), the author. I learned a lot from this repository. 
