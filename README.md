# 🏖️ MEAformer
![](https://img.shields.io/badge/version-1.0.1-blue)
[![license](https://img.shields.io/github/license/mashape/apistatus.svg?maxAge=2592000)](https://github.com/zjukg/MEAformer/blob/main/licence)
[![arxiv badge](https://img.shields.io/badge/arxiv-2212.14454-red)](https://arxiv.org/abs/2212.14454)
[![Pytorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?e&logo=PyTorch&logoColor=white)](https://pytorch.org/)
[![ACMMM](https://img.shields.io/badge/ACM%20MM-2023-%23bd9f65?labelColor=%233d4cac&color=%23dd2167)](https://www.acmmm2023.org/)

 - [*MEAformer: Multi-modal Entity Alignment Transformer for Meta Modality Hybrid*](https://arxiv.org/abs/2212.14454)
>This paper introduces MEAformer, a multi-modal entity alignment transformer approach for meta modality hybrid, which dynamically predicts the mutual correlation coefficients among modalities for more fine-grained entity-level modality fusion and alignment.

<div align="center">
    <img src="https://github.com/zjukg/MEAformer/blob/main/IMG/MEAformer.jpg" width="95%" height="auto" />
</div>

## 🔔 News
- **`2023-7` We release the [Repo](https://github.com/zjukg/UMAEA) for our paper: [`Rethinking Uncertainly Missing and Ambiguous Visual Modality in Multi-Modal Entity Alignment`](https://arxiv.org/abs/2307.16210) !** 
- **`2023-5` We preprint our paper [`Revisit and Outstrip Entity Alignment: A Perspective of Generative Models`](https://arxiv.org/abs/2305.14651) !**
- **`2023-4` We release the complete code and [data](https://drive.google.com/file/d/1VIWcc3KDcLcRImeSrF2AyhetBLq_gsnx/view?usp=sharing) for [MEAformer](https://github.com/zjukg/MEAformer) !**

<!-- >In this paper .... -->

## 🔬 Dependencies
```bash
pip install -r requirement.txt
```
#### Details
- Python (>= 3.7)
- [PyTorch](http://pytorch.org/) (>= 1.6.0)
- numpy (>= 1.19.2)
- [Transformers](http://huggingface.co/transformers/) (>= 4.21.3)
- easydict (>= 1.10)
- unidecode (>= 1.3.6)
- tensorboard (>= 2.11.0)




## 🚀 Train
- **Quick start**: Using  script file (`run.sh`)
```bash
>> cd MEAformer
>> bash run.sh
```
- **Optional**: Using the `bash command`
```bash
>> cd MEAformer
# -----------------------
# ---- non-iterative ----
# -----------------------
# ----  w/o surface  ---- 
# FBDB15K
>> bash run_meaformer.sh 1 FBDB15K norm 0.8 0 
>> bash run_meaformer.sh 1 FBDB15K norm 0.5 0 
>> bash run_meaformer.sh 1 FBDB15K norm 0.2 0 
# FBYG15K
>> bash run_meaformer.sh 1 FBYG15K norm 0.8 0 
>> bash run_meaformer.sh 1 FBYG15K norm 0.5 0 
>> bash run_meaformer.sh 1 FBYG15K norm 0.2 0 
# DBP15K
>> bash run_meaformer.sh 1 DBP15K zh_en 0.3 0 
>> bash run_meaformer.sh 1 DBP15K ja_en 0.3 0 
>> bash run_meaformer.sh 1 DBP15K fr_en 0.3 0
# ----  w/ surface  ---- 
# DBP15K
>> bash run_meaformer.sh 1 DBP15K zh_en 0.3 1 
>> bash run_meaformer.sh 1 DBP15K ja_en 0.3 1 
>> bash run_meaformer.sh 1 DBP15K fr_en 0.3 1
# -----------------------
# ------ iterative ------
# -----------------------
# ----  w/o surface  ---- 
# FBDB15K
>> bash run_meaformer_il.sh 1 FBDB15K norm 0.8 0 
>> bash run_meaformer_il.sh 1 FBDB15K norm 0.5 0 
>> bash run_meaformer_il.sh 1 FBDB15K norm 0.2 0 
# FBYG15K
>> bash run_meaformer_il.sh 1 FBYG15K norm 0.8 0 
>> bash run_meaformer_il.sh 1 FBYG15K norm 0.5 0 
>> bash run_meaformer_il.sh 1 FBYG15K norm 0.2 0 
# DBP15K
>> bash run_meaformer_il.sh 1 DBP15K zh_en 0.3 0 
>> bash run_meaformer_il.sh 1 DBP15K ja_en 0.3 0 
>> bash run_meaformer_il.sh 1 DBP15K fr_en 0.3 0
# ----  w/ surface  ---- 
# DBP15K
>> bash run_meaformer_il.sh 1 DBP15K zh_en 0.3 1 
>> bash run_meaformer_il.sh 1 DBP15K ja_en 0.3 1 
>> bash run_meaformer_il.sh 1 DBP15K fr_en 0.3 1
```

❗Tips: you can open the `run_meaformer.sh` or `run_meaformer_il.sh` file for parameter or training target modification.

## 🎯 Results

$\bf{H@1}$ Performance with the Settings: **`w/o surface & Non-iterative`** in **[UMAEA](https://github.com/zjukg/umaea)**. We modified part of the [MSNEA](https://github.com/liyichen-cly/MSNEA) to involve not using the content of attribute values but only the attribute types themselves (See [issues](https://github.com/zjukg/MEAformer/issues/3) for details):
| Method | $\bf{DBP15K_{ZH-EN}}$ | $\bf{DBP15K_{JA-EN}}$ | $\bf{DBP15K_{FR-EN}}$ |
|:------------------:|:----------------:|:----------------:|:----------------:|
|        [MSNEA](https://github.com/liyichen-cly/MSNEA)          |    .609     |     .541     |      .557     |
|        [EVA](https://github.com/cambridgeltl/eva)          |    .683     |     .669    |      .686     |
|        [MCLEA](https://github.com/lzxlin/mclea)          |    .726     |     .719     |      .719     |
|        [MEAformer](https://github.com/zjukg/MEAformer)         |    **.772**     |     **.764**     |      **.771**     |
|        [UMAEA](https://github.com/zjukg/umaea)         |    **.800**     |     **.801**     |      **.818**     |


## 📚 Dataset
❗NOTE: Download from [GoogleDrive](https://drive.google.com/file/d/1VIWcc3KDcLcRImeSrF2AyhetBLq_gsnx/view?usp=sharing) (1.26G) and unzip it to make those files **satisfy the following file hierarchy**:
```
ROOT
├── data
│   └── mmkg
└── code
    └── MEAformer
```

#### Code Path
<details>
    <summary>👈 🔎 Click</summary>
 
```
MEAformer
├── config.py
├── main.py
├── requirement.txt
├── run_meaformer.sh
├── run_meaformer_il.sh
├── run.sh
├── model
│   ├── __init__.py
│   ├── layers.py
│   ├── MEAformer_loss.py
│   ├── MEAformer.py
│   ├── MEAformer_tools.py
│   └── Tool_model.py
├── src
│   ├── __init__.py
│   ├── distributed_utils.py
│   ├── data.py
│   └── utils.py
└── torchlight
    ├── __init__.py
    ├── logger.py
    ├── metric.py
    └── utils.py
```

</details>


#### Data Path
<details>
    <summary>👈 🔎 Click</summary>
 
```
mmkg
├── DBP15K
│   ├── fr_en
│   │   ├── ent_ids_1
│   │   ├── ent_ids_2
│   │   ├── ill_ent_ids
│   │   ├── training_attrs_1
│   │   ├── training_attrs_2
│   │   ├── triples_1
│   │   └── triples_2
│   ├── ja_en
│   │   ├── ent_ids_1
│   │   ├── ent_ids_2
│   │   ├── ill_ent_ids
│   │   ├── training_attrs_1
│   │   ├── training_attrs_2
│   │   ├── triples_1
│   │   └── triples_2
│   ├── translated_ent_name
│   │   ├── dbp_fr_en.json
│   │   ├── dbp_ja_en.json
│   │   └── dbp_zh_en.json
│   └── zh_en
│       ├── ent_ids_1
│       ├── ent_ids_2
│       ├── ill_ent_ids
│       ├── training_attrs_1
│       ├── training_attrs_2
│       ├── triples_1
│       └── triples_2
├── FBDB15K
│   └── norm
│       ├── ent_ids_1
│       ├── ent_ids_2
│       ├── ill_ent_ids
│       ├── training_attrs_1
│       ├── training_attrs_2
│       ├── triples_1
│       └── triples_2
├── FBYG15K
│   └── norm
│       ├── ent_ids_1
│       ├── ent_ids_2
│       ├── ill_ent_ids
│       ├── training_attrs_1
│       ├── training_attrs_2
│       ├── triples_1
│       └── triples_2
├── embedding
│   └── glove.6B.300d.txt
├── pkls
│   ├── dbpedia_wikidata_15k_dense_GA_id_img_feature_dict.pkl
│   ├── dbpedia_wikidata_15k_norm_GA_id_img_feature_dict.pkl
│   ├── FBDB15K_id_img_feature_dict.pkl
│   ├── FBYG15K_id_img_feature_dict.pkl
│   ├── fr_en_GA_id_img_feature_dict.pkl
│   ├── ja_en_GA_id_img_feature_dict.pkl
│   └── zh_en_GA_id_img_feature_dict.pkl
├── MEAformer
└── dump
```

</details>

## 🤝 Cite:
Please condiser citing this paper if you use the ```code``` or ```data``` from our work.
Thanks a lot :)

```bigquery
@inproceedings{chen2023meaformer,
  author    = {Zhuo Chen and
               Jiaoyan Chen and
               Wen Zhang and
               Lingbing Guo and
               Yin Fang and
               Yufeng Huang and
               Yichi Zhang and
               Yuxia Geng and
               Jeff Z. Pan and
               Wenting Song and
               Huajun Chen},
  title     = {MEAformer: Multi-modal Entity Alignment Transformer for Meta Modality Hybrid},
  booktitle    = {{ACM} Multimedia},
  publisher    = {{ACM}},
  year         = {2023}
}
```


## 💡 Acknowledgement

We appreciate [MCLEA](https://github.com/lzxlin/MCLEA), [MSNEA](https://github.com/liyichen-cly/MSNEA), [EVA](https://github.com/cambridgeltl/eva), [MMEA](https://github.com/liyichen-cly/MMEA) and many other related works for their open-source contributions.

<a href="https://info.flagcounter.com/VOlE"><img src="https://s11.flagcounter.com/count2/VOlE/bg_FFFFFF/txt_000000/border_F7F7F7/columns_6/maxflags_12/viewers_3/labels_0/pageviews_0/flags_0/percent_0/" alt="Flag Counter" border="0"></a>
