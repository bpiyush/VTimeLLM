
* Install environment
```sh
conda create --name=vtimellm python=3.10
conda activate vtimellm

git clone git@github.com:bpiyush/VTimeLLM.git
cd VTimeLLM
pip install -r requirements.txt
```

* Download weights

```sh
# Download weights of CLIP from [here](https://cloud.tsinghua.edu.cn/d/6db5d02883124826aa6f/?p=%2Fcheckpoints%2Fclip&mode=list)
# Upload it to vggdev21
# rsync-to-vgg-download $PWD/ViT-L-14.pt /users/piyush/pretrained_checkpoints/VTimeLLM/

# Download Vicuna1.5-7B and ChatGLM-3-6B weights from [here](https://cloud.tsinghua.edu.cn/d/6db5d02883124826aa6f/?p=%2Fcheckpoints&mode=list)

# Unzip
tar -xvzf vtimellm-vicuna-v1-5-7b.tar.gz
tar -xvzf vtimellm-chatglm3-6b.tar.gz

# Remove the tar files
rm vtimellm-vicuna-v1-5-7b.tar.gz
rm vtimellm-chatglm3-6b.tar.gz


# rsync-to-vggdev21 $PWD/ /work/piyush/pretrained_checkpoints/LargeModels/VTimeLLM/
# symlink it in checkpoints/
ln -s /work/piyush/pretrained_checkpoints/LargeModels/VTimeLLM/ checkpoints
```