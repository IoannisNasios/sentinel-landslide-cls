# Classification for Landslide Detection


<br />  


## General
* **Competition Purpose:** Accurate landslide detection using multi-source satellite data (Sentinel-2 and Sentinel-1)
* **Type:** Image Classification
* **Platform:** Zindi
* **Competition link:** https://zindi.africa/competitions/classification-for-landslide-detection
* **Placement:** 2nd (2/267)  
* **User Name:** Ouranos  
* **System used:** Google Colab Pro
* **Solution:** [write-up](./write_up_Ouranos.pdf)  
* **Train duration:** About 40 hours on Google Colab pro
* **Inference duration:** About 3 hours on Google Colab pro

<br />  

**High Level solution description.** The final solution is an ensemble of predictions from nine classification models, comprising seven neural networks (NNs) and two gradient boosting models (GBMs). At post processing, a threshold equal to 0.49 is applied to turn probabilities to binary estimations based on OOF score.

<br />  


### System    
| Characteristic   |  Google Colab pro     | 
|------------------| ----------------------|  
| Cuda             |  12.5                 |  
| Python           |  3.11.13              |  
| Pytorch          |  2.6                  |  
| GPU              |  Tesla T4             | 
| RAM              |  50GB                 | 



### Run Code   

#### **Configuration**  
Before running the notebooks, ensure that all file paths are correctly updated as needed. Since the gradient boosting models (GBMs) were trained without GPU acceleration and the neural networks (NNs) were trained with GPU support, two separate requirements.txt files are provided, each listing the necessary libraries and compatible versions for their respective environments.  


#### **Train and Inference of Individual Models**  
To achieve the optimal solution, train all models by executing the notebooks listed below. Ensure that all necessary configurations and file paths are properly set beforehand. The order in which the notebooks are run is not important. Upon completion, the notebooks will generate out-of-fold (OOF) predictions, test probability files (test_probs), and submission files, all saved to their respective directories.  
[LightGBM](Landslide_Class_S2S1_v18bG.ipynb)  
[XGBoost](Landslide_Class_S2S1_v44G.ipynb)  
[Maxvit Tiny](Landslide_Class_S2S1_v10G.ipynb)  
[Vit Medium](Landslide_Class_S2S1_v20G.ipynb)  
[Vit pwee 2Ecnoders](Landslide_Class_S2S1_v31G.ipynb)  
[Vit pwee 2Ecnoders](Landslide_Class_S2S1_v33G.ipynb)  
[Vit pwee 3Ecnoders](Landslide_Class_S2S1_v37G.ipynb)  
[Caformer S18 3Ecnoders](Landslide_Class_S2S1_v39G.ipynb)  
[Vit Medium rope 3Ecnoders](Landslide_Class_S2S1_v46G.ipynb)  


#### **Ensemble Predictions**  
After successfully running the training notebooks, execute the following notebook to ensemble the model predictions. This step combines outputs from all trained models to generate the final predictions. (Generates submission file: Landslide_Class_S2S1_ensembleAVGv101820313337394446_THRESH0.49b.csv)  
[Ensemble](Landslide_Class_S2S1_ensembleG.ipynb)  



#### **Extra notebook - Inference**
To generate landslide predictions on any test dataset, use the following notebook. Ensure that all trained model weights are placed in the weights directory. This notebook is designed for inference only, it loads the pre-trained models, runs predictions on the input data, and performs ensembling to produce the final output. (Create solution output: AVG5THRESH0.49.csv for competition test data).  
[New test predictions](landslide-class-inf6nooof.ipynb)  


<br /> 



<br />  

