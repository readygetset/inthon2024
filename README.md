# InThon 2024
> 🏆 **2024 InThon Datathon First Prize Winner!**  
> This is the solution code for 2024 InThon Datathon hosted by the College of Informatics at Korea University.

## Task
**Multimodal - Reliable & Efficient Image Captioning with Vision-Language Models (VLMs)**

## Evaluation Metrics
### Reliability Score
- SPICE: Measures text quality by analyzing captions as combinations of objects, attributes, and relations.
- CLIPScore: Assesses image-caption consistency using CLIP embeddings, even without reference captions.
- CHAIRf: Evaluates the match between generated and actual objects, considering both precision and recall.
### Efficiency & Sustainability Weight
- Applied to the Reliability score based on the number of parameters used in model training and dataset size.
