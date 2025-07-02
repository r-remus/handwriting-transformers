This is a fork of [Handwriting-Transformers](https://github.com/ankanbhunia/Handwriting-Transformers). It's goal is to make the project
 * pip-installable and
 * easier to use as a service.

---

# :zap: Handwriting Transformers
  
<p align='center'>
  <b>
    <a href="https://ankanbhunia.github.io/Handwriting-Transformers/">Project</a>
    |
    <a href="https://arxiv.org/abs/2104.03964">ArXiv</a>
    | 
    <a href="https://openaccess.thecvf.com/content/ICCV2021/papers/Bhunia_Handwriting_Transformers_ICCV_2021_paper.pdf">Paper</a>
    | 
    <a href="https://ankankbhunia-hwt.hf.space/">Huggingface-demo</a>
    | 
    <a href="https://colab.research.google.com/github/ankanbhunia/Handwriting-Transformers/blob/main/demo.ipynb">Colab-demo</a>
  </b>
</p>
<p align="center">
  <img src=resources/figures/mainfigure.jpg width="500"/>
</p>


 ## Abstract
 
[Ankan Kumar Bhunia](https://scholar.google.com/citations?user=2leAc3AAAAAJ&hl=en),
[Salman Khan](https://scholar.google.com/citations?user=M59O9lkAAAAJ&hl=en),
[Hisham Cholakkal](https://scholar.google.com/citations?user=bZ3YBRcAAAAJ&hl=en), 
[Rao Muhammad Anwer](https://scholar.google.fi/citations?user=_KlvMVoAAAAJ&hl=en),
[Fahad Shahbaz Khan](https://scholar.google.ch/citations?user=zvaeYnUAAAAJ&hl=en&oi=ao) &
[Mubarak Shah](https://scholar.google.com/citations?user=p8gsO3gAAAAJ&hl=en)


> **Abstract:** 
>*We propose a novel transformer-based styled handwritten text image generation approach, HWT, that strives to learn both style-content entanglement as well as global and local writing style patterns. The proposed HWT captures the long and short range  relationships within the style examples through a self-attention mechanism, thereby encoding both global and local style patterns. Further, the proposed transformer-based HWT comprises an encoder-decoder attention that enables style-content entanglement by gathering the style representation of each query character. To the best of our knowledge, we are the first to introduce a transformer-based generative network for styled handwritten text generation. Our proposed HWT generates realistic styled handwritten text images and significantly outperforms the state-of-the-art demonstrated through extensive qualitative, quantitative and human-based evaluations. The proposed HWT can handle arbitrary length of text and any desired writing style in a few-shot setting. Further, our HWT generalizes well to the challenging scenario where both words and writing style are unseen during training, generating realistic styled handwritten text images.* 


## Installation

The project can now be installed via
```
pip install git+https://github.com/r-remus/handwriting-transformers
``` 

While the original repository requires Python 3.7 and PyTorch >= 1.4, this requires Python 3.9-3.12 and PyTorch >=2.7.

Pickled dataset files and models can be downloaded from [here](https://drive.google.com/file/d/16g9zgysQnWk7-353_tMig92KsZsrcM6k/view?usp=sharing) and should be extracted to ```resources/handwriting_transformers/```.


## Training

To train the model run

```bash
python src/handwriting_transformers/train.py
```

If you want to use ```wandb``` please install it and change your auth_key in the ```src/handwriting_transformers/train.py``` file (ln:4). 

You can change different parameters in the ```src/handwriting_transformers/params.py``` file.

You can train the model on any custom dataset other than IAM and CVL. The process involves creating a ```dataset_name.pickle``` file and placing it inside ```resources/handwriting_transformers``` folder. The structure of ```dataset_name.pickle``` is a simple python dictionary:

```python
{
'train': [{writer_1:[{'img': <PIL.IMAGE>, 'label':<str_label>},...]}, {writer_2:[{'img': <PIL.IMAGE>, 'label':<str_label>},...]},...], 
'test': [{writer_3:[{'img': <PIL.IMAGE>, 'label':<str_label>},...]}, {writer_4:[{'img': <PIL.IMAGE>, 'label':<str_label>},...]},...], 
}
```


## Citation

If you use the code for your research, please cite our paper:

```
@InProceedings{Bhunia_2021_ICCV,
    author    = {Bhunia, Ankan Kumar and Khan, Salman and Cholakkal, Hisham and Anwer, Rao Muhammad and Khan, Fahad Shahbaz and Shah, Mubarak},
    title     = {Handwriting Transformers},
    booktitle = {Proceedings of the IEEE/CVF International Conference on Computer Vision (ICCV)},
    month     = {October},
    year      = {2021},
    pages     = {1086-1094}
}
```

