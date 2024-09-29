# Capstone-Modul-3
Hotel Booking Demand Analysis


### Introduction

The hospitality industry, particularly hotels, often implements overbooking strategies to anticipate reservation cancellations. This strategy is increasingly facilitated by technological advancements, especially in online booking systems, which allow customers to quickly make reservations or cancellations flexibly.

Reservation cancellations play a crucial role in hotel management because, on one hand, they help maximize revenue by minimizing the potential for vacant rooms. However, on the other hand, excessive overbooking can harm the hotel's reputation if customers arrive and do not get the promised room. Therefore, the ability to predict the cancellation rate becomes very important. With accurate predictions, hotels can more effectively manage the number of rooms available for overbooking, reduce the risk of customer dissatisfaction, and maintain optimal revenue.

Advancements in data analytics and machine learning now enable hotels to predict cancellation patterns more accurately. By understanding these patterns, hotels can adjust their overbooking strategies more intelligently, thus maintaining a balance between filling available rooms and ensuring customer satisfaction. Utilizing cancellation predictions provides a competitive advantage for hospitality businesses in increasing revenue without sacrificing the quality of service provided.

### Problem Statement 

The growth of online distribution has increased by 46% from 2014 to 2018. In 2018, manual bookings shifted to online travel agents by almost 68%. The hospitality industry now faces challenges in generating revenue due to the ease of online reservation cancellations. Based on data collected in 2018, nearly 40% of expected revenue was lost due to cancellations before guest arrival. This is attributed to the ease of making and canceling reservations online. With this machine learning approach, it is hoped that the hospitality industry can optimize their overbooking strategies, minimize the risk of cancellations, and ultimately significantly increase revenue.

### Goals 

Strategi overbooking dapat berjalan efektif jika kita mampu memperkirakan jumlah pemesanan yang akan dibatalkan dengan akurat. Jika perkiraan jumlah pembatalan terlalu rendah, hal ini dapat menyebabkan banyak kamar kosong yang tidak terisi, sehingga mengurangi pendapatan. Sebaliknya, jika perkiraan pembatalan terlalu tinggi, hotel berisiko mengalami situasi overbooked, di mana pelanggan tidak mendapatkan kamar yang mereka pesan, yang dapat menurunkan tingkat kepuasan dan merusak reputasi hotel.

### Analytics Approach

The approach taken to address this issue involves creating a classification model designed to predict the likelihood of reservation cancellations. Additionally, an in-depth analysis of the data will be conducted to identify patterns that distinguish between canceled and non-canceled reservations, providing deeper insights to the company.

### Classification Algorithm 

If using a classification approach to predict reservation cancellations (booking cancellations), some commonly used algorithms include:

1. **Logistic Regression**: This algorithm is suitable for binary classification, such as predicting whether a reservation will be canceled (1) or not (0).

2. **Random Forest**: This algorithm uses multiple decision trees to make predictions. Random Forest is very good at handling data with many features and provides stable results.

3. **Gradient Boosting**: This algorithm learns from the errors of previous models and builds better models gradually. Popular variants of this algorithm are XGBoost and LightGBM, which are often used to improve prediction accuracy.

4. **Support Vector Machine (SVM)**: SVM works by dividing data into two categories (e.g., cancellation or not) by finding the best hyperplane that separates these classes.

5. **K-Nearest Neighbors (KNN)**: KNN uses proximity to other similar data to predict the class of a sample. This algorithm is often used in simple classification problems.

6. **Naive Bayes**: This algorithm is based on probability theory, assuming independence among features. It is suitable for use if the data distribution follows a certain pattern.

7. **Artificial Neural Networks (ANN)**: Neural networks can be used for classification problems with more complex data. They often provide good results, especially when the data has non-linear relationships.

The choice of algorithm depends on the complexity of the data, the size of the dataset, and the expected performance. Evaluating the performance of each model is also important to determine which algorithm is most suitable for the data being used.

### Algorithm 

Linear regression can be used for classification, although this algorithm is more commonly used for predicting continuous values. Here is an explanation of why linear regression can be applied in the context of classification, especially for predicting reservation cancellations:

### Why Use Linear Regression for Classification:

1. **Suitability for Continuous Data**: Linear regression is traditionally used to predict continuous values but can be adapted for classification by converting the output into probabilities. In this context, linear regression can provide an estimated probability of an event (e.g., the likelihood of cancellation).

2. **Sigmoid Activation Function**: To use linear regression in classification, a sigmoid activation function is typically applied to the model's output. The sigmoid function transforms the linear regression output (which can be a continuous value) into a probability between 0 and 1, which can then be used to decide the class (0 or 1) based on a certain threshold (e.g., 0.5).

3. **Simplicity and Interpretability**: Linear regression is simple and easy to understand. The model provides interpretable coefficients that show the influence of each feature on the probability of cancellation. This makes it useful for initial understanding and feature analysis.

4. **Speed and Efficiency**: Linear regression is relatively quick to train and evaluate compared to more complex classification algorithms. This can be advantageous when working with large datasets or when short training times are needed.

5. **Basis for More Complex Models**: Linear regression is often used as a starting point in the development of classification models. The results from linear regression can help in selecting or designing more complex classification models, such as logistic regression or tree-based models.

### Limitations:

1. **Linearity**: Linear regression assumes a linear relationship between features and the target, which may not always be suitable for complex classification problems. If the data does not have a linear relationship, this model may be less accurate compared to more sophisticated algorithms.

2. **Overfitting and Underfitting**: Linear regression can suffer from overfitting if it is too complex or underfitting if it is not complex enough to capture patterns in the data.

Overall, while linear regression is not the primary choice for all classification problems, it can still be used in this context with appropriate adjustments and can provide useful results for initial analysis and model development.

Target (y) : 
- 0 : Not Cancel
- 1 : Cancel

| Actual \ Prediction | Negative (0/Not Cancel) | Positive (1/Cancel) |
| --- | --- | --- |
| Negative (0/Not Cancel) | Actual not cancel, Prediction not cancel (TN)  | Actual not cancel, Prediction cancel (FP) |
| Positive (1/Cancel) | Actual cancel, Prediction not cancel (FN) | Actual not cancel, Prediction not cancel (TP) |

False negative: 
Rooms remain unrented (rooms will be empty), even though there are potential customers who could rent those rooms

False Positive: 
rooms will be overbooked, leading to a diminished hotel reputation and potentially causing customer dissatisfaction (bad hotel reputation/satisfaction), resulting in customers not renting rooms at that hotel in the future.
