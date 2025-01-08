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

If you cannot download/search the image because of some network problems:
- download image form one of below links:
  - Figshare: https://doi.org/10.6084/m9.figshare.26317273.v1  
  - Baidu Netdisk: https://pan.baidu.com/s/16TeFgBgAmZ9BiIiJcBGURw?pwd=gp6g
- Uncompress gwas.tar.gz to gwas.tar
- Go to Command (Windows sys) or Terminal (MacOS sys)
- Enter command: docker load --input downloadpath/gwas.tar
- Check image panel in Docker Desktop