## Land Use Classification using Convolutional Neural Networks
<img src='earths.png'> 

### Problem Statement:
Satellite imagery can help us find solutions to the growing number of environmental problems that we face today. It allows us to not only get a bird’s eye view of what’s around us, but also uncovers parts of the world that are rarely seen. Tapping into the potential of categorizing land cover and land use around the world means that humans can more efficiently make use of natural resources, hopefully lowering cases of waste and deprivation. But despite its potential to be incredibly useful, satellite data is massive and confusing, and making sense of it requires complex analysis. 

This project could help a variety of stakeholders, including conservationists, urban planners, and environmental scientists, survey and identify patterns in land use to see which natural areas are under threat or which areas are best for urban development. But in this case, I will tailor this project to a client that is similar to the agriculture imagery company that I currently work for. Imagery companies can use land use classification models to categorize what’s in each image and optimize their efforts towards the parts of land that are important to them. For example, an agriculture company will only want to be concerned with land that’s labelled as pasture, annual crop, or permanent crop. If a satellite is constantly taking images, this project would help save hours of time manually sorting through imagery.

In addition to sorting imagery, land use classification is important for identifying the parts of an image to which certain analyses are applied. For example, if the company has different crop stress algorithms for fields that are next to urban areas versus fields that are next to rivers, this project would help them to automate the process of applying these specialized algorithms and more effectively solve environmental problems.

### Inquiry:
Can we create a model that can classify the landscape/land use of a given image?

### Dataset Description:
For this project, I used open source EuroSAT Sentinel-2 satellite images from the German Research Center for Artificial Intelligence, which can be downloaded locally [link](http://madm.dfki.de/downloads). The dataset consists of 27,000 labeled images of 10 different land use classes:
- Annual Crop
- Forest
- Herbaceous Vegetation
- Highway
- Industrial
- Pasture
- Permanent Crop
- Residential
- River
- Sea / Lake

Each multispectral image consists of 13 different color bands that represent different wavelengths of light/color and different resolutions. These different light bands help distinguish parts of the landscape that reflect certain types of light in particular ways. Since most images don’t include special bands like Vegetation Red Edge, Coastal aerosol, or SWIR, for this project I chose to only use the red, green, and blue bands in an effort to make my model generalizable to most images.

### Project Plan
This project includes notebooks for all stages in the process: 
1. [Data preparation](https://github.com/clairemiles/land-use-classification-cnn/blob/master/0_build_rgb_dataset.ipynb)
1. [Exploratory data analysis](https://github.com/clairemiles/land-use-classification-cnn/blob/master/1_exploratory_data_analysis.ipynb)
1. [Convolutional neural network model](https://github.com/clairemiles/land-use-classification-cnn/blob/master/2_cnn_model.ipynb)
1. [CNN with model tuning](https://github.com/clairemiles/land-use-classification-cnn/blob/master/3_cnn_tuned.ipynb)

Using keras as the main machine learning library for this project, I crafted a RGB jpeg dataset from thousands of thirteen-band tif files, and used transfer learning, data augmentation, and regularization to build three different models with increasing performance.

Read the [final project report here](https://github.com/clairemiles/land-use-classification-cnn/blob/master/labeling_land_report.pdf), and view the [slides here](https://github.com/clairemiles/land-use-classification-cnn/blob/master/labeling_land_slides.pdf).
