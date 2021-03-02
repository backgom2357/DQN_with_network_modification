# DQN with Network Modification
Propose fully convolutional network with skip connection which is deeper than the network used in vanilla DQN. Apply the network to [DQN](https://www.nature.com/articles/nature14236), [DDQN](https://arxiv.org/abs/1509.06461) and [Deuling-DDQN](https://arxiv.org/abs/1511.06581). Compare the performance with vanilla algorithms in 6 Atari games. And introduce 3 useful debuging method.

# Network

![image](https://user-images.githubusercontent.com/30210944/109586121-04017c00-7b48-11eb-9a27-fbd9491d9bce.png)

With skip connection, the network can catch the details (eg. bullets, balls). Althogh layers of the network is increasing, the parameters is still smaller than the previous network (With inputs of the Atari games, the number of parameters in new network is 138,020 and in previous network is 211,620).


# 6 Atari Games
[Open AI gym Atari](https://gym.openai.com/envs/#atari)
- Breakout
- SpaceInvaders
- Pong
- Enduro
- Atlantis
- BeamRider

# Result

### Please check here - [Experiment Report (Korean)](https://www.notion.so/DQN-with-Network-Modification-08a7dff0e45c429db8b1db68b9c401b0)


### Breakout
![Untitled (1)](https://user-images.githubusercontent.com/30210944/109586529-b6d1da00-7b48-11eb-8aa8-1d409267779e.png)
Duration : 1d 19h 33m 39s

### SpaceInvaders
![Untitled](https://user-images.githubusercontent.com/30210944/109586617-e1239780-7b48-11eb-98ef-4fab651bb225.png)
Duration : 1d 4h 41m 19s

### Pong
![Untitled (2)](https://user-images.githubusercontent.com/30210944/109586661-fdbfcf80-7b48-11eb-9fbe-5279091777f4.png)
Duration : 2d 10h 7m 49s

### BeamRider
![Untitled (3)](https://user-images.githubusercontent.com/30210944/109587882-29dc5000-7b4b-11eb-9437-cab9ae2db409.png)
Duration : 3d 4h 18m 7s

### Enduro
![Untitled (4)](https://user-images.githubusercontent.com/30210944/109587952-47a9b500-7b4b-11eb-9032-f2d06778b0ae.png)
Duration : 
- Proposed : 3d 3h 7m 23s
- Vanilla : 2d 20h 14s

### Atlantis
![Untitled (5)](https://user-images.githubusercontent.com/30210944/109588035-6f008200-7b4b-11eb-8c1c-43dbb8263d24.png)
Duration :
- Proposed : 4d 48m 41s
- Vanilla : 1d 6h 9m 40s


# Useful Debuging Method
- Check Input Frames
- Check Saliency Map ([Grad-CAM](https://arxiv.org/abs/1610.02391))
- Check Log and Plot

![renders](https://user-images.githubusercontent.com/30210944/109589890-652c4e00-7b4e-11eb-94b9-cb25230ac860.gif)
![input_frames](https://user-images.githubusercontent.com/30210944/109588293-d7e7fa00-7b4b-11eb-8970-659ce1bdeca5.gif)
![saliency_map](https://user-images.githubusercontent.com/30210944/109588371-f77f2280-7b4b-11eb-8847-9f4d6e1973a4.gif)

![plots](https://user-images.githubusercontent.com/30210944/109588457-1aa9d200-7b4c-11eb-8014-cf1730d58ee3.gif)

# Usage
### Training
```
python ./DQN/train.py
```

### Test
```
python ./DQN/test.py
```

# requirements
```
tensorflow==2.2.0
scikit-learn==0.23.2
matplotlib==3.3.3
gym[atari]
opencv-python
```