# InThon 2024
> 🏆 **2024 InThon Datathon First Prize Winner!**  
> This is the solution code for 2024 InThon Datathon hosted by the College of Informatics at Korea University.

## Task
**Multimodal - Reliable & Efficient Image Captioning with Vision-Language Models (VLMs)**

## Evaluation Metrics
### ▶️ Reliability Score
- SPICE: Measures text quality by analyzing captions as combinations of objects, attributes, and relations.
- CLIPScore: Assesses image-caption consistency using CLIP embeddings, even without reference captions.
- CHAIRf: Evaluates the match between generated and actual objects, considering both precision and recall.
### ▶️ Efficiency & Sustainability Weight
- Applied to the Reliability score based on the number of parameters used in model training and dataset size.

## Method
### ▶️ Why Training Free?
**From the Perspective of Training Data:**
1. The training dataset is relatively small, with about 3,000 samples, yet it involves a comparatively large number of objects to consider (50 objects).
2. Due to the small size of the training data, outliers are expected to have a significant impact.
3. The training data lacks distinctive features and shows characteristics similar to blip's pretrain dataset, like the MS COCO dataset.
   
**From the Perspective of Efficiency:**
1. The theme of the datathon is Efficiency & Sustainability.
2. Given the time constraints typical of a datathon, there is a focus on achieving much faster speeds and higher performance compared to traditional training models.

### ▶️ Model
Salesforce/instructblip-vicuna-13b

### ▶️ Prompt-Engineering
**Baseline:** Describe this image in detail. 

**First Attempt:**
List and describe all identifiable objects, people, and actions occurring within the image, focusing on their appearance, spatial arrangement, and interactions.

**Second Attempt: Two-Step Prompting**
1. The evaluation objects are assessed for its presence in the image with a response of yes or no.
2. A query is then generated using the objects identified as present in the image: "Describe the image with the following objects: {object list from step 1}. These objects are highly likely to be in the image. Focus on their appearance, spatial arrangement, and interactions."
🚨 Despite going through more steps and being slower, it shows slightly lower performance compared to the first attempt!

**Final Attempt: Combination of first attempt & second attempt**
Observing the strong performance in the first attempt, it was determined that making the model describe identifiable objects was the key factor for the improved results, leading to the following modification of the first stage.
1. Describe the background of the image, describe every object in the image and its appearance in detail.
2. Simply describe following objects in the image: {object list from step 1}. Focus on their appearance, color, actions, and interactions with surrounding objects. 
