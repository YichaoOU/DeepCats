# Ohio University Big Data Club, DeepCats

Our models are simple modifications based on YT8M-2017 winner's solution: https://github.com/antoine77340/Youtube-8M-WILLOW. 

The best model obtained is the LightVLAD model, which ranked at 18/394 in YT8M-2018. The training parameters are:

- batch_size=200
- base_learning_rate=0.0001
- learning_rate_decay=0.8
- netvlad_cluster_size=150
- netvlad_hidden_size=1250
- audio_cluster_size=20
- moe_num_mixtures=4

There are several patterns we found:

1. Increase moe_num_mixtures to 4 (default is 2) can improve score around 0.003, and the model size only increases 50M.

2. If trained too many iterations (> 200K), the score decreased.

3. Adding dropout didn't increase score

4. Adding more layers didn't increase score

5. Tried relu, relu6, and Leaky ReLu, didn't increase score.

6. netVLAD is the second best comparing to LightVLAD.

7. In the LightVLAD model, number of hidden neurons is more important than netvlad_cluster_size.

To see the actual command, check out the job files in each folder.
