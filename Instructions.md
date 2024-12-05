The following are instructions to execute the MarineGPT model. 
Based on the available instruction on the GitHub page of MarineGPT (<https://github.com/hkust-vgd/MarineGPT/blob/main/README.md>). There are several options as to which of the models to use (Vicuna 7B/Vicuna13B/Gemma 2B/Gemma7B). This implementation uses the Vicuna 7B model.  

1. Navigate to  your chosen project directory
2. Clone the github repository

**git clone [https://github.com/hkust-vgd/MarineGPT**](https://github.com/hkust-vgd/MarineGPT)**

3. Install python version 3.9

**sudo apt install python3.9**

**sudo apt install python3.9-venv**

4. Navigate into the MarineGPT folder

**cd MarineGPT**

5. Create virtual environment using python 3.9

**python3.9 -m venv marinegptenv**

6. Activate environment:

**source marinegptenv/bin/activate**

7. Install the required packages within the virtual environment (Due to the difficulties faced in executing the original yaml file provided by the MarineGPT authors, as some builds are incompatibile with the most recent python version).

**pip install omegaconf numpy torch gradio torchvision iopath timm opencv-python webdataset transformers decord SentencePiece bitsandbytes accelerate**

8. Download the LLM weights into MarineGPT (this project is using the Vicuna 7B weights)

**git lfs clone [https://huggingface.co/Vision-CAIR/vicuna-7b**](https://huggingface.co/Vision-CAIR/vicuna-7b)**

    1. Adjustments must be done to the following file: MarineGPT/marinegpt/configs/models/**marinegpt.yaml**
    2. Modify the path to the llama model in line 16 to the path of the downloaded Vicuna 7B weights.
**llama\_model: “vicuna-7b”**


9. Download the training checkpoint file and place within the MarineGPT directory (https://drive.google.com/file/d/1udhmjDQfx3zmyXROd6-iQN60zxpIccxS/view?usp=sharing)

    1. Navigate to MarineGPT/eval\_configs/marinegpt\_eval.yaml
    2. In line 11, change the checkpoint path to the downloaded checkpoint.
**ckpt: ‘marinegpt\_vicuna\_7B\_stage2\_ckpt.pth’**

10. Replace demo.py, train.py and MarineGPT/marinegpt/models/marinegpt.py scripts with the ones present in this repository.

11. To run the model:

**python demo.py --cfg-path eval\_configs/marinegpt\_eval.yaml  --gpu-id 0**






