---
title:  "7 Ways to Convert Velox emd Files"
modified: 2020-08-18
categories:
  - articles
tags:
  - Image processing
toc: true
toc_sticky: true
---

![avatat](https://lh3.googleusercontent.com/qnGJGJgzbDXRfkj-dLzoIU7AO_sW-QMkTIW7WPS_yIonExPAl2LRbLnZLA6ExQ9-RwRkovEJTxzgsvlluFb0R1J70RhZXfNi2GpCW-iUsjh-HFJl_Vbvk2m5yRZeaOr0ihQWunaX21P9Z9aWGFGf_l__wtaDHt99Tf7Lxo4luYOa21oZb-p9--scCHYQtntZB6ND2mICjSXUS4Tq7ksyQdn8P7Dn2uM011I1SDWL-MyB1BXnxT2XdtveGrSjOUwNUUTnqFH3EgegFWzrRxTnQD5K3MI2oqxFIjjaymEhnatYRt7ZyBc__bsMKbsP4OKCxTelI67YrkgGx7s2zfPVlStRujHQwAoTA7UoRKR2EN4rmZMyx_O3-9yKjoFj4huQCo68CWqUVtI87qrE-XTPPtEUF4jtw4chnBe0XGLX0ybSj_QW-tZXtxHvV1QrrK1nGswMhIK4yf3DTP1vKc1wwFkQVuaFhE4peAMJ5y0pZQUHhZqVe2_ICawdZ0p6SI4Q0dBLv1UzeEBMY5HaY715k8Ih9iy73WDDhK3c05i_bjrC4ph6Js_P2gMkkK5k-VbLXedUT0oG6kYhiA1wdTb26vnfg-e_WHHc4sWBhijxszuKJ8HWs9ZKl1CVGOtPEICACWTxybGnY5M6tYWDJtE-T4a9HYahBaoYrzxTUPZTXMVAB74AUrChHfqKxgTH7xc=w1906-h888-no?authuser=0)

## TL; DR
> **I summarized 7 ways to convert the emd file from Velox developed by Thermo Fisher (former FEI).**

1. If you can code in Python, see section 3 or 4, you’ll have the full access to the emd data (image, spectrum) and metadata  (acquisition parameters)
2. If you can code in Matlab, see sectio 6. No metadata support for now.
3. If you don’t feel like coding and just want a simple exe to batch convert emd into 16-bit tiff, see section 2. It has the ability to export every slice in image series as well.
4. If you’re lucky enough with an access to Velox, section 1 provides some exportation details. Besides, Velox software provides the easiest and fastest way to export images with scale bars.
5. If you’re testing your limit and having a lot of patience, see section 6 or 7 for imageJ and DM approaches.

## 1. Velox software
## 2. Thermo Fisher application: BatchExport.exe
> https://drive.google.com/drive/folders/1GUMdgoPHuM-uUK-vXvd24eKWqZpAldZ7?usp=sharing

## 3. Python: Hyperspy

## 4. Python: OpenNCEM

## 5. Matlab: EMD reader

## 6. ImageJ: EMD class reader
> https://drive.google.com/drive/folders/1cxRaU6qhh-1PWrfy6QwUnNhLPKKaoVg8?usp=sharing

## 7. Digital Micrograph: Gatan DM EMD reader
> https://www.felmi-zfe.at/dm_script/velox-files-reader/

* You’ll also need HDF5 plug-in for DM https://github.com/niermann/gms_plugin_hdf5
Some skills of building C libraries with command line are needed
* **I haven’t test this yet.**
