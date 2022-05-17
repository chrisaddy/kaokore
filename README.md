# KaoKore Dataset

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-blue.svg)](https://creativecommons.org/licenses/by-sa/4.0/)  

📚 [Read the paper](https://arxiv.org/abs/2002.08595)  to learn more about Kaokore dataset, our motivations in making them, as well as creative usage of it! The paper is in [the proceedings](http://computationalcreativity.net/iccc20/proceedings/) of the Eleventh International Conference on Computational Creativity, ICCC’20.


**Dataset History** We are keeping expanding the dataset. Besides adding more images, all other settings remain the same.The update history is:

* Version `1.3`: Exapnded to `9683` images. Most recent version
* Version `1.2`: Exapnded to `8848` images. Most recent version
* Version `1.1`: Exapnded to `8573` images. 
* Version `1.0`: `5552` images. The initial relase.

_Note that the classification and the genertive results here and in the paper still correspond to the version `1.0` of our dataset._

## The Dataset

_KaoKore_ is a novel dataset of face images from Japanese illustrations along with multiple labels for each face, derived from the [_Collection of Facial Expressions_](http://codh.rois.ac.jp/face/).

_KaoKore_ dataset is build based on the [_Collection of Facial Expressions_](http://codh.rois.ac.jp/face/), which results from an effort by the ROIS-DS Center for Open Data in the Humanities (CODH) that has been publicly available since 2018.
It provides a dataset of cropped face images extracted from Japanese artworks publicly available from National Institute of Japanese Literature, Kyoto University Rare Materials Digital Archive and Keio University Media Center from the Late Muromachi Period (16th century) to the Early Edo Period (17th century) to facilitate research into art history, especially the study of artistic style. It also provides corresponding metadata annotated by researchers with domain expertise.

KaoKore dataset contains image files, each being an color (RGB) image of size `256 x 256` as well as two sets of labels _gender_ and _social status_. The most recent version contains `8848` images.

<p align="center">
  <img src="images/fig/dataset_example.png" width='768'>

  <br>
  Example of the <em>KaoKore</em> dataset, showing various faces in diverse yet coherent artisticstyles.
</p>

<p align="center">
  <img src="images/fig/label_example.png" width='512'>
  
  <br>
  Labels (labels.csv) available in the dataset along with exemplary images belonging to each labels.
</p>

## Get the data 💾

🌟 You can run [`python3 download.py`](download.py) download KaoKore datasets. The default setting downloads the initial version `1.0` of the dataset. **To try newer versions (e.g. `1.3`), please use `python3 download.py --dataset_version 1.3`**. For version numbers plese refer to **Dataset History** above.
Also, see the output of `download.py --help` for more details. 

It is known that some conda installations may have trouble looking for SSL certificates. If that is the case, you could use `download.py --ssl_unverified_context`, **at your own risk and only if you know what you are doing**, to disable the certificate verification. Also it is reported that the default downlaod concurrency `--threads 16` may be too high for some network/machines. In that case please try a lower one.

Please note that we **intentionally** did not include image data into the dataset so that image providers can check which images are used. We request not to create a derived dataset including image data for user's convenience.

### The Data Loaders

Data loaders for _Pytorch_ and _TensorFlow_ are available in code folder.

## Benchmarks & Results 📈

We provide quantitative results on the supervised machine learning tasks of gender and social status prediction from KaoKore images. (Keras classification code is available in code folder)

Have more results to add to the table? Feel free to submit an [issue](https://github.com/rois-codh/kaokore/issues/new) or [pull request](https://github.com/rois-codh/kaokore/compare)! (update the link****)

|Model                            | Gender| Status | Credit
|---------------------------------|-------|--------|-----|
|VGG11    |92.03% | 78.74% | [alantian](https://github.com/alantian) |
|AlexNet    |91.27% | 78.93% | [alantian](https://github.com/alantian) |
|ResNet-18    |92.98% | 82.16% | [alantian](https://github.com/alantian) |
|ResNet-34    |93.55% | 84.82% | [alantian](https://github.com/alantian) |
|MobileNet-v2    |95.06% | 82.35% | [alantian](https://github.com/alantian) |
|DenseNet-121   |94.31% | 79.70% | [alantian](https://github.com/alantian) |
|Inception-v3    |96.58% | 84.25% | [alantian](https://github.com/alantian) |

## Generative Models Demo Videos

Please download generative model demo video from here.

1. [Learning to painting](http://codh.rois.ac.jp/face/dataset/demo/learning-to-painting_drawings.zip)
2. [Intrinsic style transfer drawing](http://codh.rois.ac.jp/face/dataset/demo/intrinsic-style-transfer_drawings.zip)

## Citing KaoKore dataset

If you use any of the Kaokore datasets in your work, we would appreciate a reference to our paper:

**KaoKore dataset etc. Yingtao Tian et al. [arXiv:2002.08595](https://arxiv.org/abs/2002.08595)** update the link

```
@inproceedings{tian2020kaokore,
    title      = "{KaoKore: A Pre-modern Japanese Art Facial Expression Dataset}",
    author     = {Yingtao Tian and Chikahiko Suzuki and Tarin Clanuwat and Mikel Bober-Irizar and Alex Lamb and Asanobu Kitamoto},
    booktitle  = "Proceedings of the International Conference on Computational Creativity",
    year       = "2020",
    pages      = "415--422"
}
```

## License

Both the dataset itself and the contents of this repo are licensed under a permissive  [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) license, except where specified within some benchmark scripts. CC BY-SA 4.0 license requires attribution, and we would suggest to use the following attribution to the KaoKore dataset.

"KaoKore Dataset" (collected by CODH from multiple organizations), doi:10.20676/00000353
