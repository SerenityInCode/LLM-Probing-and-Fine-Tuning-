# LLM Interpretability with Probing and Fine-Tuning

> **Comparative study on how fine-tuning reshapes the internal representations of Large Language Models (LLMs)**

---

## 📚 Description
This project explores **NLP interpretability** by addressing the *black-box* problem of Large Language Models.  
It investigates **how a model’s internal representations of linguistic features are structured** and how these representations **change after fine-tuning for a high-level task**.

We perform a **two-stage methodology** to compare the internal knowledge of:
* a **pre-trained model** and
* a **model fine-tuned for a readability prediction task**.

---

## 🧪 Methodology

### 1️⃣ Baseline Probing
- Probe a **pre-trained BERT-base model** to establish a baseline.
- Train simple diagnostic probes on embeddings from each of the model’s 12 layers.
- Measure how well the model encodes features such as **number of characters, syllables, and POS tags**.

### 2️⃣ Fine-Tuning
- Fine-tune a **DistilBERT-base model** on the **OneStopEnglishCorpus** for a **high-level readability prediction task**  
  *(Flesch-Kincaid Grade Level and Flesch Reading Ease)*.
- Implement a **5-fold cross-validation** pipeline for robust evaluation.

### 3️⃣ Comparative Probing
- Re-run the probing experiments on the **fine-tuned DistilBERT models**.
- Compare the new layer-wise results with the baseline to **quantify representational shifts** caused by fine-tuning.

---

## 🔑 Key Findings
- **Hierarchical Encoding:** The pre-trained model encodes low-level features in early layers and abstract features in deeper layers.  
- **Representational Shift:** Fine-tuning reorganizes internal representations, making foundational features more accessible and robust across layers.  
- **Trade-offs:** Fine-tuned DistilBERT excels as a task specialist but does not always outperform simple probes on a larger pre-trained model.

---

## 🛠 Technical Stack
- **Language:** Python  
- **Frameworks:** PyTorch, [Hugging Face Transformers](https://huggingface.co/transformers/)  
- **Libraries:** scikit-learn, datasets, pandas, numpy, conllu, textstat  
- **Tools:** Jupyter Notebooks, GPU (for accelerated training)

---

## 📂 Datasets
- **[UD English-EWT Corpus](https://universaldependencies.org/)** – Diagnostic dataset for probing with ground-truth word-level features.  
- **[OneStopEnglishCorpus](https://github.com/nishkalavallabhi/OneStopEnglishCorpus)** – For readability prediction fine-tuning.  
- **[MRC Psycholinguistic Database](https://websites.psychology.uwa.edu.au/school/MRCDatabase/)** – For probing abstract psycholinguistic properties.


