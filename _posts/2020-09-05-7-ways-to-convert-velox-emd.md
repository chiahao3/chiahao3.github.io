---
title:  "7 Ways to Convert Velox emd Files"
modified: 2020-09-05
categories:
  - articles
tags:
  - Image processing
  - Velox
toc: true
toc_sticky: true
---

![avatat](https://lh3.googleusercontent.com/qnGJGJgzbDXRfkj-dLzoIU7AO_sW-QMkTIW7WPS_yIonExPAl2LRbLnZLA6ExQ9-RwRkovEJTxzgsvlluFb0R1J70RhZXfNi2GpCW-iUsjh-HFJl_Vbvk2m5yRZeaOr0ihQWunaX21P9Z9aWGFGf_l__wtaDHt99Tf7Lxo4luYOa21oZb-p9--scCHYQtntZB6ND2mICjSXUS4Tq7ksyQdn8P7Dn2uM011I1SDWL-MyB1BXnxT2XdtveGrSjOUwNUUTnqFH3EgegFWzrRxTnQD5K3MI2oqxFIjjaymEhnatYRt7ZyBc__bsMKbsP4OKCxTelI67YrkgGx7s2zfPVlStRujHQwAoTA7UoRKR2EN4rmZMyx_O3-9yKjoFj4huQCo68CWqUVtI87qrE-XTPPtEUF4jtw4chnBe0XGLX0ybSj_QW-tZXtxHvV1QrrK1nGswMhIK4yf3DTP1vKc1wwFkQVuaFhE4peAMJ5y0pZQUHhZqVe2_ICawdZ0p6SI4Q0dBLv1UzeEBMY5HaY715k8Ih9iy73WDDhK3c05i_bjrC4ph6Js_P2gMkkK5k-VbLXedUT0oG6kYhiA1wdTb26vnfg-e_WHHc4sWBhijxszuKJ8HWs9ZKl1CVGOtPEICACWTxybGnY5M6tYWDJtE-T4a9HYahBaoYrzxTUPZTXMVAB74AUrChHfqKxgTH7xc=w1906-h888-no?authuser=0)

## TL; DR
> **I summarized 7 ways to convert the emd files generated from Velox that developed by Thermo Fisher (former FEI).**

1. If you can code in Python, see section 3 or 4, you’ll have the full access to the emd data (image, spectrum) and metadata  (acquisition parameters)
2. If you can code in Matlab, see sectio 5. No metadata support for now.
3. If you don’t feel like coding and just want a simple exe to batch convert emd into 16-bit tiff, see section 2. It has the ability to export every slice in image series as well.
4. If you’re lucky enough with an access to Velox, section 1 provides some exportation details. Besides, Velox software provides the easiest and fastest way to export images with scale bars.
5. If you’re testing your limit and having a lot of patience, see section 6 or 7 for imageJ and DM approaches.

## 1. Velox software
> [Velox software](https://www.thermofisher.com/us/en/home/electron-microscopy/products/software-em-3d-vis/velox-software.html)
* Developed by Thermo Fisher, **licensed software**
* Provides the simplest way to export images with scale bar, data bar, and any annotations
* Export emd images into png, jpg, 8-bit(32-bit RGBA) TIFF and 16-bit TIFF
* It can NOT export the image series. Only the last frame will be exported.
* See future post for detailed comparison of 3 export options available by Velox

## 2. Thermo Fisher application: BatchExport.exe
> [Google Drive Link](https://drive.google.com/drive/folders/1GUMdgoPHuM-uUK-vXvd24eKWqZpAldZ7?usp=sharing)
* Developed by Thermo Fisher, Windows application
* I accidently found this in the Velox folder. I think this is fast, simple, and straight forward. **Probably the easiest approach among every other ones if you just want the image real quick.**
* It outputs the 16-bit raw TIFF with the option of subfolders.
* It also outputs each raw frame from an image series emd file into a separate folder.

## 3. Python: HyperSpy
> [http://hyperspy.org/](http://hyperspy.org/hyperspy-doc/current/user_guide/io.html?highlight=data%20format#emd)
* **Kudos to HyperSpy team that makes this wonderful package!**
* By far, I think this is the most flexible and useful approach. You can get every image, spectrum, metadata, and do all kinds of post-processing easily.
* Hyperspy has its GUI option as well.
* Some Python knowledge is needed, but it's definitely worth it.
* I'll upload my own emd2tiff script to my GitHub repo in the near future

## 4. Python: OpenNCEM
> [https://github.com/ercius/openNCEM/tree/master/ncempy/io](https://github.com/ercius/openNCEM/tree/master/ncempy/io)
* Developed by Dr. Peter Ercius from NCEM
* A collection of packages and tools for electron microscopy data analysis
* **I haven’t test this yet.**

## 5. Matlab: EMD reader
> [https://github.com/sezelt/matlab_Velox_reader](https://github.com/sezelt/matlab_Velox_reader)
* Developed by Dr. Steven Eric Zeltmann from NCEM
* Matlab function that import image data from Velox emd
* **I haven’t test this yet.**

## 6. ImageJ: EMD class reader
> [Google Drive Link](https://drive.google.com/drive/folders/1cxRaU6qhh-1PWrfy6QwUnNhLPKKaoVg8?usp=sharing)
* Develped by Thermo Fisher
* **ImageJ plugin so that you can read emd files**
* Drag-and-Drop would not work
* 1 emd file at a time
*  Only for images, no metadata, no EDS support

## 7. Digital Micrograph: Gatan DM EMD reader
> [https://www.felmi-zfe.at/dm_script/velox-files-reader/](https://www.felmi-zfe.at/dm_script/velox-files-reader/)
* Developed by Dr. Mingjian Wu from FAU Erlangen-Nuremberg
* You’ll also need HDF5 plug-in for DM https://github.com/niermann/gms_plugin_hdf5
Some skills of building C libraries with command line are needed
* **Parse metadata into image tags**
* **I haven’t test this yet.**

## Summary

Importing the experimental data is crucial but can also be quite tedius if your only option is to right-click and export every emd file. Thanks to all the developer that built these wonderful tools for us to easily access the information without much limitation! Let me know if you have any other tricks to share, so that I can make this post more complete, much appreciated!
