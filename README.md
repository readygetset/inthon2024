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
   
### Prompt-Engineering
**First Attempt**
**Second Attempt**
**Final Attempt**
