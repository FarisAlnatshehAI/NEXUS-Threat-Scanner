NEXUS Threat Scanner 
An intelligent engine for detecting and classifying malicious URLs using Machine Learning and Hybrid Feature Engineering techniques.

Project Overview
The NEXUS Threat Scanner is an End-to-End ML Pipeline solution designed to analyze URLs in real-time to determine whether they are safe or pose a security threat. The system relies on an interactive user interface that receives a URL, performs extraction and analysis in milliseconds, and delivers a block/allow decision accompanied by a Confidence Level.

Domain Knowledge
This engine has been trained to detect and classify four main types of URLs, reflecting a precise understanding of the nature of cyber threats:

  Benign: Safe and secure URLs for use.
  
  Phishing: Phishing links designed to steal sensitive data and user accounts.
  
  Malware: Links dedicated to downloading and spreading malicious software.
  
  Defacement: Links targeting the hacking and defacing of legitimate website content.
  

Feature Engineering & NLP
The system employs a hybrid approach to feature extraction to ensure maximum accuracy in understanding the "behavior" of the URL:

  Heuristics (Manually Extracted Features): Calculating precise indicators such as Entropy, URL length, number of directories, and using Regular Expressions  (Regex) to detect direct IP usage or suspicious words.
  
  Text Analysis (TF-IDF): Using n-grams technique at the character level (Char-level) to discover hidden linguistic patterns in malicious URLs.
  
  Sparse Matrices: scipy.sparse.hstack was used to merge manual features (after applying MinMax Scaling) with the TF-IDF outputs, which significantly contributed to reducing memory consumption and accelerating the training process.
  

Modeling & Evaluation
The models were trained and evaluated on a massive dataset exceeding one million links (1M+ URLs).
To avoid the trap of bias towards benign data (which constituted the majority), relying solely on overall Accuracy was avoided. Instead, the focus was placed on F1-Score and Recall metrics to ensure the system's efficiency and strictness in capturing malicious threats.
Algorithms Used: Several advanced models were trained and compared, including: XGBoost, LightGBM, CatBoost, and LinearSVC.

Installation & Usage
To run the interface and test the system locally on your machine, please follow these steps:

1. Clone the repository and install the required libraries:
pip install -r requirements.txt

2. Run the Streamlit interface:
streamlit run app.py
(Note: If you are using cloud environments like Colab or Kaggle, make sure to place your token in a tool like Ngrok to expose the interface port).

Contributors
This project was built as part of the requirements for the Machine Learning course at Al al-Bayt University.

Faris Alnatsheh - www.linkedin.com/in/faris-alnatsheh-8aba4838b

Mashhour Abu Suneineh - www.linkedin.com/in/mashhour-abusninh-737113356
