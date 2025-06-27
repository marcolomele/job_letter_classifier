# Job Letter Classifier

The **Job Letter Classifier** is a machine learning system designed to analyze motivational, statement, or reference letters for job applications. It extracts key features from the letter, generates a job description, and predicts the most suitable job type and job category for the applicant. The system leverages both deep learning models and OpenAI's GPT API for natural language understanding and classification.

## 🛠️ Features
- **Automated Feature Extraction:** Uses OpenAI's GPT to extract job-relevant features from free-form letters.
- **Job Description Generation:** Summarizes extracted features into a brief job description.
- **Job Type Prediction:** Classifies the job type (e.g., Full-time, Part-time, Internship, etc.) using an LSTM-based neural network.
- **Job Category Prediction:** Classifies the job category (e.g., IT, Marketing, Finance, etc.) using a separate LSTM-based neural network.
- **Customizable Keyword Mapping:** Assigns job categories based on keywords in job descriptions.

## ✅ Requirements
- Python 3.x
- Jupyter Notebook or Google Colab
- [openai](https://pypi.org/project/openai/) (v0.28)
- [cohere](https://pypi.org/project/cohere/)
- [tiktoken](https://pypi.org/project/tiktoken/)
- pandas, numpy, scikit-learn, nltk, keras, tensorflow, dateutil

Install dependencies (if running locally):
```bash
pip install openai==0.28 cohere tiktoken pandas numpy scikit-learn nltk keras tensorflow python-dateutil
```

## 🕹️ Usage
1. **Prepare Data:**
   - Place your job postings CSV files (`job_postings.csv`, `updated_postings.csv`) in the working directory.
   - The notebook processes and merges these files, engineering features and assigning categories based on keywords.
   - The processed file is saved as `updated3_postings.csv`.

2. **Run the Notebook:**
   - Open `job_letter_classifier.ipynb` in Jupyter or Google Colab.
   - Install required libraries (first code cell).
   - Upload the processed CSV when prompted.

3. **Train Models:**
   - The notebook trains two LSTM models:
     - One for job type classification (7 classes)
     - One for job category classification (18 classes)
   - Training takes approximately 40 minutes in total.

4. **Letter Analysis and Prediction:**
   - Enter your OpenAI API key in the designated cell.
   - Input a motivational or reference letter when prompted.
   - The system extracts features, generates a job description, and predicts the most suitable job type and category.

5. **Results:**
   - The predictions are displayed in a pandas DataFrame.

### Example Workflow
1. **Upload Data:**
   - Upload `updated3_postings.csv` when prompted.
2. **Train Models:**
   - Run the training cells for job type and category.
3. **Analyze Letter:**
   - Enter your letter in the input prompt.
   - View the extracted job description and predicted job type/category.

## ⚠️ Notes
- Running the entire notebook takes about 60 minutes (data import, training, and prediction).
- If the OpenAI API returns an empty response, simply re-run the cell.
- The notebook is designed for demonstration and may require adaptation for production use.

## 🔑 License
This project is licensed under the MIT License.
