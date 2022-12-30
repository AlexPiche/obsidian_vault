### Mujoco 

  

No spectral norm, and no action normalization, but using layer norm work best. 

best MSE is attain with spectral norm, layer, and min_max act norm
  ![[Screen Shot 2022-11-10 at 11.24.51 AM.png]]

![[Screen Shot 2022-11-10 at 11.25.23 AM.png]]
![[Screen Shot 2022-11-10 at 11.25.53 AM.png]]
Bigger learning rates slightly improve performance, but sometimes smaller learning rates improve performance eg on hopper medium replay. No effect on the mean input grad.

  
Gradient penalty of 100 help on hopper medium replay, see [https://wandb.ai/abi/l4dc_submission?workspace=user-apiche](https://wandb.ai/abi/l4dc_submission?workspace=user-apiche)**