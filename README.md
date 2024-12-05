# How to run the Model
1- Download the original MarineGPT  
https://github.com/hkust-vgd/MarineGPT  
(use Vicuna)  
2- Replace the files from this Git  
3- Navigate to the MarineGPT file  
4- Download the checkpoint into the root of MarineGPT  
https://drive.google.com/file/d/1udhmjDQfx3zmyXROd6-iQN60zxpIccxS/view?usp=sharing  
4- Run   
```
python demo.py --cfg-path eval_configs/marinegpt_eval.yaml  --gpu-id 0
```
