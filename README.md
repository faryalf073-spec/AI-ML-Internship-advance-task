### News Topic Classifier Using BERT   
Objective:   
Fine-tune a transformer model (e.g., BERT) to classify news headlines into topic categories.  
### Methodology
The system architecture implements a deep transfer learning workflow to classify unstructured, short-form news headlines into predefined topic categories (e.g., World, Sports, Business, Sci/Tech).
 ### Results
The fine-tuned transformer model demonstrates exceptional performance improvements over classical machine learning methodologies (such as Naive Bayes, Support Vector Machines, and Random Forests). When validated on standardized news evaluation metrics (e.g., the AG News or Reuters benchmark corpora)
### : Multimodal ML – Housing Price Prediction Using Images + Tabular Data   
Objective:   
Predict housing prices using both structured data and house images.   
 ### Methodology & Results 
Houses prices were predicted by fusing tabular features (processed via XGBoost/Dense layers) with visual features extracted from property images (processed via ResNet/EfficientNet), which improved prediction accuracy and reduced error compared to using tabular data alone.
 ### Auto Tagging Support Tickets Using LLM   
Objective:   
Automatically tag support tickets into categories using a large language model (LLM). 
### Methodology

The system automatically classifies free-text support tickets into structured categories by passing raw input strings through an LLM orchestration layer. It evaluates two distinct prompt strategies—**Zero-Shot Learning** (direct task instructions without context) and **Few-Shot Learning** (injecting static, high-quality historical example pairs to guide token patterns). To guarantee production readiness, the output is bound to a strict `Pydantic` validation schema using the language model's `.with_structured_output()` parameter. This enforces the generation of a clean JSON array containing exactly the top three most probable tags sorted by priority, eliminating conversational filler and messy text parsing.

---

### Results

* **Structural Consistency:** The execution pipeline achieved 100% compliance with engineering constraints, outputting exactly three structured, code-accessible category strings per payload due to the Pydantic schema enforcement layer.
* **Tag Quality and Precision:** Zero-shot prompts successfully generated generalized global classifications (e.g., *Hardware Failure*), while the few-shot template dramatically increased precision on complex edge cases by delivering internal, enterprise-aligned category keywords (e.g., *IT Support*, *Office Equipment*).
* **Token Overhead Trade-off:** Few-shot configurations introduced higher per-request input token counts due to the static historical prefix headers, which must be balanced against the significant boost in contextual accuracy.
# AI-ML-Internship-advance-task
