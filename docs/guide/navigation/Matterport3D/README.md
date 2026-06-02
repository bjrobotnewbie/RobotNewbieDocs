# Matterport3D

- [website](https://niessner.github.io/Matterport/)

## Summary

### **Abstract**

Access to large, diverse RGB-D datasets is critical for training RGB-D scene understanding algorithms. However, existing datasets still cover only a limited number of views or a restricted scale of spaces. In this paper, we introduce Matterport3D, a large-scale RGB-D dataset containing 10,800 panoramic views from 194,400 RGB-D images of 90 building-scale scenes. Annotations are provided with surface reconstructions, camera poses, and 2D and 3D semantic segmentations. The precise global alignment and comprehensive, diverse panoramic set of views over entire buildings enable a variety of supervised and self-supervised computer vision tasks, including keypoint matching, view overlap prediction, normal prediction from color, semantic segmentation, and scene classification.

### **Paper**

A. Chang, A. Dai, T. Funkhouser, M. Halber, M. Niessner, M. Savva, S. Song, A. Zeng, Y. Zhang
**[Matterport3D: Learning from RGB-D Data in Indoor Environments](https://arxiv.org/pdf/1709.06158.pdf)**
International Conference on 3D Vision (3DV 2017)
Paper | [arXiv (low res) ](https://arxiv.org/pdf/1709.06158.pdf)| Supplemental Material

```
@article{Matterport3D,
  title={Matterport3D: Learning from RGB-D Data in Indoor Environments},
  author={Chang, Angel and Dai, Angela and Funkhouser, Thomas and Halber, Maciej and Niessner, Matthias and Savva, Manolis and Song, Shuran and Zeng, Andy and Zhang, Yinda},
  journal={International Conference on 3D Vision (3DV)},
  year={2017}
}
```

### **Dataset Download**

Please fill and sign the [Terms of Use](http://kaldir.vc.in.tum.de/matterport/MP_TOS.pdf) agreement form and send it to [matterport3d@googlegroups.com](mailto:matterport3d@googlegroups.com) to request access to the dataset.

### **Code**

Please check the [git repository](https://github.com/niessner/Matterport) for a detailed introduction to the dataset and code for several vision tasks.

### **Explore the dataset**

Use the web interface [here](https://aspis.cmpt.sfu.ca/scene-toolkit/scans/matterport3d/houses) to browse the dataset.

### **Changelog**

* **2018-06-29** : Updated .house files to fix problem with room bboxes (also fixes membership of objects in rooms)

### **Contact**

Please contact us at [matterport3d@googlegroups.com](mailto:matterport3d@googlegroups.com) if you have any questions
