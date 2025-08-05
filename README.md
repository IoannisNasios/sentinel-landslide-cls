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

**High Level solution description.** The solution is based on the ensemble of 9 classification models predictions. Each one of these predictions is a simple average of all possible flips (TTA=4) of every fold (5 folds). At post processing, a threshold equal to 0.49 is applied to turn probabilities to binary estimations based on OOF.

<br />  


### System    
| Characteristic   |  Google Colab pro     | 
|------------------| ----------------------|  
| Cuda             |  12.5                 |  
| Python           |  3.11.13              |  
| Pytorch          |  2.6                  |  
| GPU              |  Tesla T4             | 
| RAM              |  50GB                 | 



### Configuration  
Modify the notebooks to specify the paths. Trained model weights should be 
placed in trained_weights directory.  


#### **Train Models Notebooks**  
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
Run the following notebook to ensemble predictions of individual models  
[Ensemble](Landslide_Class_S2S1_ensembleG.ipynb)  



#### **Extra notebook**
Use the following notebook to any similar test dataset to get new estimations provided that trained model weights are in the model weights directory.  
[New test predictions](landslide-class-inf6nooof.ipynb)  


<br /> 



<br />  

