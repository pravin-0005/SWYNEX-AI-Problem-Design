# AI-Based Student Query Classification System



## 1. Problem Statement




College students frequently have questions related to academics, examinations, attendance, fees, placements, hostel facilities, and other college services.




Manually identifying the category of every student query can be time-consuming for administrative staff.




The proposed AI system classifies a student's text query into a predefined category. This classification can later be used to automatically route the query to the appropriate department or provide a relevant FAQ response.




### Example




**Input:**




> "How many days of attendance are required to attend the semester examination?"




**Predicted Category:**




> Attendance




---




## 2. Target User




The primary users are:




* College students
* College administrative staff
* Student support/help-desk teams




Students submit questions in natural language, while the classification system identifies the most appropriate category.




---




## 3. AI Use Case




### Task Type




**Text Classification / Natural Language Processing (NLP)**




The model receives a text query and predicts one of the predefined categories.




### Categories




The initial system will contain six categories:




1. Academic
2. Attendance
3. Examination
4. Fees
5. Placement
6. General




The number of categories can be expanded in future versions.




---




## 4. Data Source




A small labeled dataset will be created for the initial prototype.




Each record will contain:




| Field    | Description                               |
| --- | ----------------------------------------- |
| query    | Student's question                        |
| category | Correct category assigned to the question |




### Example Dataset




| Query                                         | Category    |
| --------------------------------------------- | ----------- |
| "When does the semester start?"               | Academic    |
| "What is the minimum attendance requirement?" | Attendance  |
| "When is the internal examination?"           | Examination |
| "How can I pay my semester fees?"             | Fees        |
| "When will campus placements begin?"          | Placement   |
| "Where can I contact the college office?"     | General     |




The initial dataset can contain approximately **100–300 labeled queries** for experimentation.




For a production system, a much larger dataset collected from real student support queries would be required.




---




## 5. Input and Output




### Input




A natural-language student question.




Example:




> "When will the placement training start?"




### Output




A predicted category.




```text
Placement
```




The system may also return a confidence score.




Example:




```text
Category: Placement
Confidence: 0.91
```




---




## 6. Proposed AI Approach




The initial prototype can use a traditional NLP classification pipeline.




### Pipeline




```text
Student Query
     ↓
Text Cleaning
     ↓
Text Vectorization
     ↓
Classification Model
     ↓
Predicted Category
     ↓
Confidence Score
```




Possible text vectorization techniques:




* TF-IDF
* Bag of Words




Possible classification algorithms:




* Logistic Regression
* Naive Bayes
* Support Vector Machine




For the initial prototype, **TF-IDF + Logistic Regression** can be used as the baseline approach because it is lightweight and suitable for a small labeled dataset.




---




## 7. Constraints




The prototype has the following constraints:




### Dataset Size




The initial dataset is relatively small, which may limit model generalization.




### Language




The first version will primarily target English-language queries.




### Ambiguous Queries




Some questions may belong to multiple categories.




For example:




> "Will low attendance affect my eligibility for the exam?"




This involves both Attendance and Examination.




The prototype will assign a single primary category.




### Informal Language




Students may use abbreviations, spelling mistakes, or informal language.




Example:




> "exam fee last date?"




The system should eventually be tested against such variations.




### Limited Categories




Only a small number of predefined categories will be supported initially.




---




## 8. Success Criteria




The system will be evaluated using a held-out test dataset.




The primary evaluation metrics will be:




### Accuracy




Percentage of queries classified correctly.




**Target:** ≥ 85%




### Precision




Measures how many predictions for a category are actually correct.




**Target:** ≥ 80%




### Recall




Measures how many queries belonging to a category are correctly identified.




**Target:** ≥ 80%




### F1-Score




The harmonic mean of precision and recall.




**Target:** ≥ 80%




The target values are prototype-level goals and would need to be validated against a representative real-world dataset before deployment.




---




## 9. Evaluation Strategy




The dataset will be divided into:




* 80% training data
* 20% testing data




The model will be trained only on the training set.




The test set will be kept separate and used to evaluate the final model.




A confusion matrix will also be used to identify categories that the model frequently confuses.




For example:




```text
                   Predicted
                Academic Attendance Exam
Actual Academic      ✓        -       -
Actual Attendance    -        ✓       -
Actual Exam          -        -       ✓
```




---




## 10. Baseline




A simple baseline can be established before using machine learning.




For example, a keyword-based approach could classify queries based on words such as:




```text
attendance → Attendance
fee/payment → Fees
exam/test → Examination
placement/job → Placement
```




The ML model will then be compared against this baseline.




The objective is to determine whether the machine-learning approach provides better and more robust classification.




---




## 11. Risks and Limitations




Potential issues include:




* Small training dataset
* Class imbalance
* Ambiguous questions
* Spelling mistakes
* Unseen questions
* Questions containing multiple topics
* Changes in college terminology




The model should not automatically provide critical administrative information unless the information has been verified from an authoritative college source.




---




## 12. Future Improvements




The prototype can later be extended with:




1. A larger real-world dataset
2. Multilingual support
3. Transformer-based NLP models
4. Automatic FAQ retrieval
5. Retrieval-Augmented Generation (RAG)
6. Confidence-based human escalation
7. Web or mobile interface
8. Analytics dashboard
9. Feedback-based model improvement




The final system could become a student-support chatbot that first classifies the question and then retrieves an appropriate answer from an approved college knowledge base.




---




## 13. Expected Outcome




The expected outcome is a lightweight NLP system capable of automatically categorizing common student questions.




The prototype will demonstrate:




* Practical AI problem identification
* Dataset design
* NLP classification
* Model evaluation
* Definition of measurable success criteria




The project is designed as a small proof-of-concept that can later be developed into a complete student-support AI assistant.




---




## Expected Outcome




The expected outcome is a lightweight NLP system capable of automatically categorizing common student questions.




The prototype will demonstrate:




* Practical AI problem identification
* Dataset design
* NLP classification
* Model evaluation
* Definition of measurable success criteria




The project is designed as a small proof-of-concept that can later be developed into a complete student-support AI assistant.
