# Latent Probing for Toxicity Detection
# 🌍 Project Overview

This project investigates whether toxicity-related information can be detected from the internal representations of a language model.

Using the Jigsaw Toxic Comment Classification Challenge dataset, we examine toxic and non-toxic comments and use Gemma to obtain latent representations from different layers of the model.

We then train linear probes on these representations to investigate how effectively toxicity can be detected from the model's internal states.

The goal is to better understand where and how toxicity-related information is represented within a language model, while exploring an efficient approach to toxicity detection and model interpretability.
# 🎯 Objectives
- Prepare and preprocess the Jigsaw toxicity dataset for latent probing experiments.
- Run the Gemma language model on the selected text samples.
- Extract hidden representations from different layers of Gemma.
- Train linear probes to classify toxic and non-toxic inputs using the extracted representations.
- Compare probe performance across different model layers.
- Evaluate the effectiveness of latent representations for toxicity detection.
- Investigate the relationship between model depth and the accessibility of toxicity-related information.
# ⚙️ Tools & Libraries
-Python
-Pandas
-NumPy
-Scikit-learn
-PyTorch
-Hugging Face Transformers
-Gemma
-Google Colab
-Jupyter Notebooks
-Matplotlib / Seaborn
# 📊 Dataset

Source: Jigsaw Toxic Comment Classification Challenge

The dataset contains comments labelled for different forms of toxicity.

Key attributes
id
comment_text
toxic
severe_toxic
obscene
threat
insult
identity_hate
# Data used in this project

The project uses the first 200 rows of the original train.csv dataset for the latent probing experiment.

The subset was obtained using:

df = pd.read_csv(url).head(200)

The resulting dataset is stored in the repository's data/ directory.

Important: We should only say the resulting dataset is stored there after you've actually uploaded the CSV.

# 🧠 Latent Probing Approach

This is the section that is particularly important for your project.

What is latent probing?

Latent probing is a technique used to investigate what information is encoded in the internal representations of a machine learning model.

Instead of directly using the original text, we examine the hidden representations produced by Gemma.

Pipeline
Input Comment
      ↓
    Gemma
      ↓
Hidden Representations
      ↓
Representations from Different Layers
      ↓
    Linear Probe
      ↓
Toxic / Non-Toxic

The probes allow us to investigate whether toxicity-related information is already present in the model's internal representations.

# 🤖 Model
Gemma

Gemma is used as the language model from which we extract latent representations.

For each input, the model processes the text and produces internal representations at different layers.

These representations are then provided to a simple classifier—the linear probe.

Linear Probe

A linear classifier is trained using the extracted representations.

The purpose is not to make the probe itself highly complex, but to determine whether the information needed for toxicity classification is linearly accessible in the model's representations.

# 📈 Evaluation

We evaluate the probes using appropriate classification metrics, such as:

Accuracy
Precision
Recall
F1-score

We also compare performance across different Gemma layers to determine where toxicity-related information appears to be most accessible.

We'll put your actual results here once your team has finished the experiments.

# 🧩 Experimental Workflow
Jigsaw Dataset
      ↓
Select 200 Samples
      ↓
Preprocessing
      ↓
Gemma Tokenization
      ↓
Run Inputs Through Gemma
      ↓
Extract Hidden States
      ↓
Select Model Layers
      ↓
Train Linear Probes
      ↓
Evaluate Probes
      ↓
Compare Layer Performance
# 🧠 Insights & Expected Outcomes

The project aims to provide insights into:

Whether toxicity can be detected from latent representations.
Which Gemma layers contain the most useful toxicity-related information.
How toxicity-related information changes across model depth.
Whether simple linear probes can effectively extract this information.
The potential usefulness of latent probing for AI safety and interpretability research.

# 📜 Acknowledgment

This project was developed as part of the AI Saturdays Lagos Machine Learning Program. We acknowledge the support of our mentors, instructors, teammates, and cohort peers throughout the project.

# 🔗 References

Jigsaw Toxic Comment Classification Challenge
Hugging Face dataset repository
Gemma documentation/paper
Relevant latent probing / interpretability research
AI Saturdays Lagos
