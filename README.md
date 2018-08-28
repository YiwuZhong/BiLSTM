# Setup

0. Install python3.6, pytorch 0.3.1 and CUDA 9.0. 

1. Download [data materials](https://drive.google.com/file/d/1pny0iRpTUch_vp2Q15dE4RajezZuOlC2/view?usp=sharing). Put all glove files into ```data/``` folder. Put all json and h5 files into ```data/stanford_filtered/```. Download the VG images [part1](https://cs.stanford.edu/people/rak248/VG_100K_2/images.zip) [part2](https://cs.stanford.edu/people/rak248/VG_100K_2/images2.zip). Extract these images to "data/visual_genome/VG_100K/" and link to them in `config.py` (eg. currently I have ```VG_IMAGES = '/home/yiwuzhong/motifs/data/visual_genome/VG_100K'```).

2. You'll also need to fix your PYTHONPATH, like: ```export PYTHONPATH=/home/yiwuzhong/motifs```, which can be added to ```~/.bashrc``` file.

3. Compile everything. run ```make``` in the main directory

4. Change and run ```bash ./scripts/refine_for_detection.sh 2``` under the ```motifs``` folder. Before running the script, modify the ```-ckpt``` where we download the pretrained model, and ```-save_dir``` where we save our checkpoints. Also, we can change ```-nepoch``` to determine how many epoches we're going to train. You can also download the "triplet margin loss" checkpoint [here](https://drive.google.com/file/d/1T_lCIyunF4xd3tXSsMbASdAaJs_5OP_b/view?usp=sharing). And original sgdet checkpoint is [here](https://drive.google.com/file/d/1BMnw2NGERUCrZ8ZMAyEeZnhhcJ-x_1EU/view?usp=sharing).

5. Evaluate: Run ```bash ./scripts/eval_models_sgdet.sh 2```.

7. During training, codes will generate ckpt and "tripscore.txt".

# help

Code for Neural Motifs: Scene Graph Parsing with Global Context (CVPR 2018)

This repository contains data and code for the paper [Neural Motifs: Scene Graph Parsing with Global Context](https://arxiv.org/abs/1711.06640v2) - now updated for the CVPR camera ready! this should be the same as what's available via the CVPR site when that appears, just it has the supplemental section rolled into the same PDF. For the project page (as well as links to the baseline checkpoints), check out [rowanzellers.com/neuralmotifs](https://rowanzellers.com/neuralmotifs). If the paper significantly inspires you, we request that you cite our work:

### Bibtex

```
@inproceedings{zellers2018scenegraphs,
  title={Neural Motifs: Scene Graph Parsing with Global Context},
  author={Zellers, Rowan and Yatskar, Mark and Thomson, Sam and Choi, Yejin},
  booktitle = "Conference on Computer Vision and Pattern Recognition",  
  year={2018}
}
```



