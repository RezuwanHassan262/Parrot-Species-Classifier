## Parrot-Species-Classifier

An image classifier model that can classify 50 parrot species with 91% accuracy. 
[Click here](https://rezuwanhassan262.github.io/Parrot-Species-Classifier/) for live demo.

fast ai and resnet34 were used to predict images of 50 different parrot species.

The project goal was to build an image classification model and deploy it on the web that can successfully classify 50 different parrot species.

The types are following: <br><br>

| Species                       | Species                    | Species                    |Species                            |Species                          |       
|:------------------------------|:---------------------------|:---------------------------|:----------------------------------|:--------------------------------|	
| 1. african grey parrot        | 11. cockatiels             | 21. hooded parrot          | 31. puerto rican amazon           | 41. scarlet macaw	              |       
| 2. australian king parrot     | 12. crimson rosella        | 22. hyacinth macaw         | 32. rainbow lorikeet              | 42. senegal parrot              |  
| 3. blue lorikeet              | 13. cuban amazon           | 23. kea                    | 33. red-breasted parakeet         | 43. spixs macaw	                |        
| 4. blue-and-yellow macaw      | 14. eclectus parrot        | 24. kākāpō                 | 34. red-crowned amazon	          | 44. sun conure	                |       
| 5. blue-headed parrot         | 15. galah                  | 25. lovebirds              | 35. red-crowned parakeet	        | 45. thick-billed parrot	        |        
| 6. budgerigar                 | 16. golden parakeet        | 26. monk parakeet          | 36. red-fan parrot                | 46. turquoise-fronted amazon    |        
| 7. burrowing parrot           | 17. great green macaw      | 27. orange-winged amazon   | 37. red-shouldered macaw          | 47. vernal hanging parrot       |   
| 8. caique parrot              | 18. great hanging parrot   | 28. palm cockatoo          | 38. red-tailed black cockatoos    | 48. white cockatoo              |        
| 9. catalina macaw             | 19. greater vasa parrot    | 29. parrotlet              | 39. rose-ringed parakeet          | 49. yellow-collared macaws      |        
| 10. chestnut-fronted macaw    | 20. hahn_s macaws          | 30. plum-headed parakeet   | 40. saint vincent amazon          | 50. yellow-headed amazon        |       

## Data collection & Dataset Preparation

Data Collection: The data was collected by downloading images from the web using each of the parrot class names from DuckDuckGo search of fastbook module 
DataLoader: fastai DataBlock API were used to set up the DataLoader and Resnet34 was used and later fine tuned multiple times.
Data Augmentation: fastai provides default data augmentation which operates in GPU.
Details can be found in notebooks/1_Parrots_classifier_data_prep.ipynb

## Training and Data Cleaning

Training: Fine-tuned a resnet34 model for 5 epochs and got upto 91% accuracy.
Data Cleaning: This part took the highest time. Since the collected data were from browser, there were many noises. Also, there were images that contained Animations, adds as well as there were garbage data that contains irrelevent subjects. I used the fastai ImageClassifierCleaner to clean and update the data. I cleaned the data after each training or finetuning iteration, except for the final iteration, which was the final version of the model. 



## Model Deployment

The final model was deployed in HuggingFace Spaces using Gradio App. The implementation can be found in deployment [here](https://rezuwan-parrot-classifier.hf.space/?)


![Model deployment on huggingface spaces screenshot](https://raw.githubusercontent.com/RezuwanHassan262/Parrot-Species-Classifier/main/images/s1.PNG) 
























## Run Locally:

1. Clone the repository

```
git clone https://github.com/RezuwanHassan262/Parrot-Species-Classifier 
```

2. Go to the project directory

```
cd Parrot-Species-Classifier 
```

3. Initialize and activate Virtual Environment

```
virtualenv --no-site-packages  venv
source venv/bin/activate
```

4. Install dependencies

```
pip install -r requirements.txt
```


