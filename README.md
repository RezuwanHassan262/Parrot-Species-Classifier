## Parrot-Species-Classifier

An image classifier model that can classify 50 parrot species with 91% accuracy. 
[Click here](https://rezuwan-parrot-classifier.hf.space/?) for live demo.

fast ai and resnet34 were used to predict images of 50 different parrot species.

The project goal was to build an image classification model and deploy it on the web that can successfully classify 50 different parrot species.

The types are following: <br><br>

| Species                       | Species                    | Species                    |Species                            |Species                          |Species                          |       
|:------------------------------|:---------------------------|:---------------------------|:----------------------------------|:--------------------------------|:--------------------------------|	
| 1. african grey parrot        | 11. caique parrot          | 21. golden parakeet        | 31. major mitchell_s cockatoo     | 41. red crowned parakeet        |51. senegal parrot               |       
| 2. australian king parrot     | 12. catalina macaw         | 22. great green macaw      | 32. monk parakeet                 | 42. red fan parrot              |52. spixs macaw                  |
| 3. australian night parrot    | 13. chestnut-fronted macaw | 23. great hanging parrot   | 33. musk lorikeet'                | 43. red lory                    |53. sulpher crested cockatoo	    |
| 4. bare eyed cockatoo         | 14. citron cockatoo        | 24. greater vasa parrot    | 34. palm cockatoo                 | 44. red rumped parrot           |54. sun conure	                  |
| 5. blue and yellow macaw      | 15. cockatiels             | 25. hahn_s macaws          | 35. parrotlet                     | 45. red shouldered macaw	      |55. thick billed parrot          |
| 6. blue headed parrot         | 16. crimson rosella        | 26. hooded parrot          | 36. plum headed parakeet          | 46. red tailed black cockatoos  |56. turquoise fronted amazon	    |
| 7. blue lorikeet              | 17. cuban amazon           | 27. hyacinth macaw         | 37. puerto rican amazon           | 47. rose ringed parakeett       |57. umbrella cockatoo	          |
| 8. brown hooded parrot        | 18. eclectus parro         | 28. kea                    | 38. rainbow lorikeet              | 48. saint vincent amazon        |58. vernal hanging parrot        |
| 9. budgerigar                 | 19. galah cockatoo         | 29. kākāpō                 | 39. red breasted parakeet         | 49. salmon crested cockatoo     |59. yellow collared macaws       |
| 10. burrowing parrot          | 20. gang gang cockatoo     | 30. lovebirds              | 40. red crowned amazonn           | 50. scarlet macaw               |60. yellow-headed amazon         |





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


![Model deployment on huggingface spaces screenshot](https://raw.githubusercontent.com/RezuwanHassan262/Parrot-Species-Classifier/main/images/app_screenshot.PNG) 


## API integration on different websites

The deployed model API is integrated [here](https://parrot-classifier-60.netlify.app/) in netlify pages Website. Implementation and other details can be found in the docs folder.


![API integration of huggingface spaces screenshot](https://raw.githubusercontent.com/RezuwanHassan262/Parrot-Species-Classifier/main/images/three.png)
