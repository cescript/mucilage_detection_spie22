# Mucilage Detection from Hyperspectral and Multispectral Satellite Data

Mucilage also called sea snot or sea saliva is a collection of mucus-like organic matter found in the sea. Although not harmful in the beginning, when mucilage increases over time, it covers the sea creatures and forms thick layers in the sea. Its existence and long duration change the oxygen balance in the seas, reduce biodiversity, fisheries, and tourism. Since April 2021, mucilage has emerged as both an ecological and economical problem in Turkey, spreading over an area of kilometers, clogging the fishing nets, causing problems in marine vessels, and disrupting the industry. These findings indicate that mucilage monitoring, early detection, and intervention before the economic and ecological damages grow out of proportion is quite necessary. Through the analysis of satellite data, it is possible to observe the existence of mucilage as thin, extended layers of white substance. Therefore, in this work, we analyze the Sentinel-2 multispectral data and PRISMA hyperspectral data to detect the mucilage in the early stages through the use of both traditional as well as deep learning algorithms. Our results indicate that it is possible to detect mucilage from satellite data with high accuracy, saving time and money for the cleaning efforts.

![Sentinel Mucilage Detection](web_images/results_SENTINEL_389_556_303.jpg)

## Using the Project

- Open `CreateConfigurationFile.m` and change the `SentinelDatasetFolder` and `PrismaDatasetFolder` to the local folders where the downloaded zip files are located.

- Run `RunAll.m` file to create a configuration file, multispectral image dataset, train models, and evaluate the results of the models.

- At the end of the `RunAll.m` function, you will see the evaluation results of the algorithms on the Sentinel-2 and PRISMA datasets.

```
SENTINEL
Model: U-Net, TPR at FPR: 0.878 / 0.050 Threshold: 0.1194
Model: Random Forest, TPR at FPR: 0.843 / 0.050 Threshold: 0.5151
Model: Linear Regression, TPR at FPR: 0.419 / 0.050 Threshold: 0.4912
Model: Vescovi Index, TPR at FPR: 0.185 / 0.050 Threshold: 0.7322

PRISMA
Model: U-Net, TPR at FPR: 0.872 / 0.050 Threshold: 0.5183
Model: Random Forest, TPR at FPR: 0.898 / 0.050 Threshold: 0.6931
Model: Linear Regression, TPR at FPR: 0.821 / 0.050 Threshold: 0.4546
Model: Vescovi Index, TPR at FPR: 0.338 / 0.050 Threshold: 0.6982
```

## Citation
If you use this code for your research, please consider citing:

```
@inproceedings{10.1117/12.2622287,
    author = {Bahri Abaci and Murat Dede and Seniha Esen Yuksel and Mete Yilmaz},
    title = {{Mucilage detection from hyperspectral and multispectral satellite data}},
    volume = {12094},
    booktitle = {Algorithms, Technologies, and Applications for Multispectral and Hyperspectral Imaging XXVIII},
    editor = {Miguel Velez-Reyes and David W. Messinger},
    organization = {International Society for Optics and Photonics},
    publisher = {SPIE},
    keywords = {Multispectral, Hyperspectral, Sentinel-2, PRISMA, Mucilage, Sea snot, Sea saliva, Deep learning},
    year = {2022},
    doi = {10.1117/12.2622287},
    URL = {https://doi.org/10.1117/12.2622287}
}
```

## Test Model on Image
- Run `TestModelsOnImage.m` file to see the results of all models on selected source files.

|True Color Image                                                                                       |U-Net                                                                                       |Random Forest                                                                                       |Linear Regression                                                                                       |Vescovi Index                                                                                       |
|:----------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------:|
|07-05-2021                                                                                |07-05-2021                                                                                 |07-05-2021                                                                                          |07-05-2021                                                                                              |07-05-2021                                                                                    |
|![20210507](web_images/results/S2B_MSIL2A_20210507T085559_N0300_R007_T35TPE_20210507T192808_0_tci.jpg)|![20210507](web_images/results/S2B_MSIL2A_20210507T085559_N0300_R007_T35TPE_20210507T192808_1_unet.jpg)|![20210507](web_images/results/S2B_MSIL2A_20210507T085559_N0300_R007_T35TPE_20210507T192808_2_random_forest.jpg)|![20210507](web_images/results/S2B_MSIL2A_20210507T085559_N0300_R007_T35TPE_20210507T192808_3_linear_regression.jpg)|![20210507](web_images/results/S2B_MSIL2A_20210507T085559_N0300_R007_T35TPE_20210507T192808_4_vescovi.jpg)|
|09-05-2021                                                                                |09-05-2021                                                                                 |09-05-2021                                                                                          |09-05-2021                                                                                              |09-05-2021                                                                                    |
|![20210509](web_images/results/S2A_MSIL2A_20210509T084601_N0300_R107_T35TPE_20210509T115513_0_tci.jpg)|![20210509](web_images/results/S2A_MSIL2A_20210509T084601_N0300_R107_T35TPE_20210509T115513_1_unet.jpg)|![20210509](web_images/results/S2A_MSIL2A_20210509T084601_N0300_R107_T35TPE_20210509T115513_2_random_forest.jpg)|![20210509](web_images/results/S2A_MSIL2A_20210509T084601_N0300_R107_T35TPE_20210509T115513_3_linear_regression.jpg)|![20210509](web_images/results/S2A_MSIL2A_20210509T084601_N0300_R107_T35TPE_20210509T115513_4_vescovi.jpg)|
|12-05-2021                                                                                |12-05-2021                                                                                 |12-05-2021                                                                                          |12-05-2021                                                                                              |12-05-2021                                                                                    |
|![20210512](web_images/results/S2A_MSIL2A_20210512T085601_N0300_R007_T35TPE_20210512T133202_0_tci.jpg)|![20210512](web_images/results/S2A_MSIL2A_20210512T085601_N0300_R007_T35TPE_20210512T133202_1_unet.jpg)|![20210512](web_images/results/S2A_MSIL2A_20210512T085601_N0300_R007_T35TPE_20210512T133202_2_random_forest.jpg)|![20210512](web_images/results/S2A_MSIL2A_20210512T085601_N0300_R007_T35TPE_20210512T133202_3_linear_regression.jpg)|![20210512](web_images/results/S2A_MSIL2A_20210512T085601_N0300_R007_T35TPE_20210512T133202_4_vescovi.jpg)|
|14-05-2021                                                                                |14-05-2021                                                                                 |14-05-2021                                                                                          |14-05-2021                                                                                              |14-05-2021                                                                                    |
|![20210514](web_images/results/S2B_MSIL2A_20210514T084559_N0300_R107_T35TPE_20210514T113538_0_tci.jpg)|![20210514](web_images/results/S2B_MSIL2A_20210514T084559_N0300_R107_T35TPE_20210514T113538_1_unet.jpg)|![20210514](web_images/results/S2B_MSIL2A_20210514T084559_N0300_R107_T35TPE_20210514T113538_2_random_forest.jpg)|![20210514](web_images/results/S2B_MSIL2A_20210514T084559_N0300_R107_T35TPE_20210514T113538_3_linear_regression.jpg)|![20210514](web_images/results/S2B_MSIL2A_20210514T084559_N0300_R107_T35TPE_20210514T113538_4_vescovi.jpg)|
|17-05-2021                                                                                |17-05-2021                                                                                 |17-05-2021                                                                                          |17-05-2021                                                                                              |17-05-2021                                                                                    |
|![20210517](web_images/results/S2B_MSIL2A_20210517T085559_N0300_R007_T35TPE_20210517T112912_0_tci.jpg)|![20210517](web_images/results/S2B_MSIL2A_20210517T085559_N0300_R007_T35TPE_20210517T112912_1_unet.jpg)|![20210517](web_images/results/S2B_MSIL2A_20210517T085559_N0300_R007_T35TPE_20210517T112912_2_random_forest.jpg)|![20210517](web_images/results/S2B_MSIL2A_20210517T085559_N0300_R007_T35TPE_20210517T112912_3_linear_regression.jpg)|![20210517](web_images/results/S2B_MSIL2A_20210517T085559_N0300_R007_T35TPE_20210517T112912_4_vescovi.jpg)|
|19-05-2021                                                                                |19-05-2021                                                                                 |19-05-2021                                                                                          |19-05-2021                                                                                              |19-05-2021                                                                                    |
|![20210519](web_images/results/S2A_MSIL2A_20210519T084601_N0300_R107_T35TPE_20210519T115101_0_tci.jpg)|![20210519](web_images/results/S2A_MSIL2A_20210519T084601_N0300_R107_T35TPE_20210519T115101_1_unet.jpg)|![20210519](web_images/results/S2A_MSIL2A_20210519T084601_N0300_R107_T35TPE_20210519T115101_2_random_forest.jpg)|![20210519](web_images/results/S2A_MSIL2A_20210519T084601_N0300_R107_T35TPE_20210519T115101_3_linear_regression.jpg)|![20210519](web_images/results/S2A_MSIL2A_20210519T084601_N0300_R107_T35TPE_20210519T115101_4_vescovi.jpg)|


