---
title: EasyOmics Install
category: Software Install
order: 2
---

After installing Docker users need to follow these steps:
- Open the Docker Desktop application.
- Skip sign up (Optional)
- Search for yuhan2000 and pull (download) the latest image yuhan2000/easyomics:latest

<div align=center><img src="../../figures/image-13.png" width="80%" /></div>

If you cannot download/search the image because of some network problems (mainly caused by the Great Firewall in China), you can download the image from the following links:
- download image form one of below links:
  - Figshare: https://doi.org/10.6084/m9.figshare.26317273.v2 
  - Baidu Netdisk: https://pan.baidu.com/s/1ZcNgnN1Iqs1p-TGY9nrWkg?pwd=n4a6
- Uncompress easyomics.tar.gz to easyomics.tar 

[tutorial video link of below steps](https://www.bilibili.com/video/BV1mVveeREqS?vd_source=3223be254b7729f362a7c9fd14e43925&p=3&spm_id_from=333.788.videopod.episodes)

- Go to Command (Windows sys) or Terminal (MacOS sys)
- Enter command: docker load --input downloadpath/easyomics.tar
- Check image panel in Docker Desktop