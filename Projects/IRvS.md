# Does Layer norm help?
## Layer norm between skip connections
reuslts are worst than without layer norm, particularly on the kitchen env.
![[Screen Shot 2022-09-27 at 10.40.09 AM.png]]
## Layer norms within skip connections
## No layer norm

https://wandb.ai/abi/tuning_september_normtanh
act_norm: "min_max"
uniform_buffer: 0.05
activation: "relu"
lr: 0.001
rtg_norm: "norm_tanh"
rtg_uniform_buffer: 0
![[Screen Shot 2022-09-27 at 10.43.31 AM.png]]
# Does more gradient steps help pass 100k?

