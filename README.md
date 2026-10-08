# Xiaohongshu(RedNoe)-credibility-analysis

## Research on an Automatic Credibility Evaluation Model for AI-Generated Multimodal Content: The Case of Xiaohongshu

Author: Yuting Wang  
Course: FIT5145 Data Science Foundations  

The original assignment for this project only implemented basic text and image analysis, but I plan to further expand it into an in-depth study combining LLM and multimodal methods. The following is the complete design description.

---

### Project Objectives

Utilize natural language processing and image understanding technologies to automatically identify untrustworthy AI-generated image-text content on social media platforms, thereby enhancing user trust and content quality.

---

### Project Module Design and Expansion Strategy

#### 1. Image-Text Consistency Detection

Objective: Identify whether the image and text semantics match, detecting false content where the image does not align with the text.

- Use CLIP to extract image and text embeddings;
- Calculate semantic similarity to determine consistency;
- Analyze image content summaries and compare them with the original user text to enhance model interpretability.

Tools: CLIP / BLIP2, sentence-transformers

---

#### 2. Credibility Signal Extraction from Text

Objective: Identify potential promotional, false, or manipulative language in text.

- Extract features such as length, sentiment, and emoji/hashtag density;
- Detect promotional/manipulative language;
- Build polynomial logistic regression or random forest models to predict credibility scores;
- Perform “credibility rewriting” on portions of text to analyze linguistic structure differences.

Tools: HuggingFace Transformers, sklearn, pandas

---

#### 3. User Behavior Analysis (User Behavior & Metadata Patterns)

Objective: Identify bot accounts or accounts engaged in bulk posting through metadata patterns.

- Calculate posting frequency, time intervals, and content repetition rates;
- Construct time series analysis charts to identify “batch generation” signals;
- Perform cluster analysis (e.g., DBSCAN) to identify “matrix accounts”;

Tools: seaborn, sklearn, pandas

---

#### 4. LDA Topic Modeling and Content Quality Mapping (Topic Modeling)

Objective: Explore the intrinsic connection between “topics” and “credibility.”

- Use LDA/BERTopic to obtain post topics;
- Analyze the average credibility score and emotional extremity under each topic;
- Summarize topic semantic features, user psychology, and false proportion.

Tools: Gensim, BERTopic, seaborn

---

### Future Directions for the Project

- Migrate to a Python framework;
- Apply multimodal LLM;
- Conduct modeling on real social platform data;

---

### Current Version Limitations

- The R language implementation is a simplified version;
- Advanced NLP/NLU models are not implemented;
- Please refer to `Yuting_34264353_Assignment3_report.pdf` for the original output.

---

### Attachments

- `Yuting_34264353_Assignment3_report.pdf`: Original analysis report  
- `Yuting_34264353_Assignment3`: Original assignment code  
- `README.md`: This documentation file

