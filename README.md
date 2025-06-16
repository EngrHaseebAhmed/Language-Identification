# Language-Identification
The objective of this project is to implement a NLP(Natural Language Based) based Language Identification System that can automatically detect the language of a given sentence. The focus is on identifying four languages: English, Urdu, Russian, and Chinese.
1. Data Collection
The dataset was obtained from the Hugging Face Dataset Willi 2018 it contains 235 different languages and I filtered my desired languages (English, Urdu, Russian and Chinese):
•	df_train – Training set containing labeled sentences.
•	df_test – Testing set for evaluating model performance.
Each dataset contains two columns:
•	sentence – The actual text input sentence in different languages
•	language – The corresponding language label (e.g., English, Urdu, etc.).
________________________________________
2. Text Preprocessing
Preprocessing is a crucial step in language detection to reduce noise and improve model performance. A custom clean_text function was implemented to clean each sentence by:
•	Removing digits
•	Removing punctuation and special characters
•	Collapsing multiple spaces into a single space
•	Stripping leading/trailing whitespaces
3. Feature Extraction Using TF-IDF
To convert textual data into numeric form, TF-IDF (Term Frequency - Inverse Document Frequency) features were extracted. Since character-level patterns are more effective for language detection, character n-grams ranging from 1 to 5 were used.



4. Model Training and Evaluation
A Multinomial Naive Bayes model was selected for training due to its effectiveness and speed on text classification tasks.
The model was evaluated using accuracy and a classification report, which includes precision, recall, and F1-score for each language.
Accuracy: 0.991

Classification Report:
               precision    recall  f1-score   support

     Chinese       1.00      0.98      0.99       500
     English       0.97      1.00      0.98       500
     Russian       1.00      1.00      1.00       500
        Urdu       1.00      0.99      0.99       500

    accuracy                           0.99      2000
   macro avg       0.99      0.99      0.99      2000
weighted avg       0.99      0.99      0.99      2000

7. Results and Conclusion
•	The trained language detection model achieved an accuracy of 99%, demonstrating excellent performance on the four selected languages.
•	The use of character-level TF-IDF features proved highly effective for language modeling.
•	The system is capable of detecting the language of unseen sentences in real-time with high confidence.
