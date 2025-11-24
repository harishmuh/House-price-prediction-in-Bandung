![image](https://github.com/harishmuh/House-price-prediction-in-Bandung/blob/main/images/bandung%20scenary%20banner.PNG?raw=true)


# 🏠 Bandung House Price Prediction with Machine Learning


### **📌 Overview**

This project builds a machine learning model to predict residential house prices in Bandung, Indonesia, using scraped property listing data.
The model helps [RancangBangun123](https://rancangbangun123.com/) (RB123), a construction & architecture company, provide transparent price insights to clients and compare construction cost vs. market value.


### **🎯 Business Goal**

Many RB123 clients ask:

“Berapa harga pasar rumah dengan spesifikasi ini di Bandung?”

“Apakah biaya pembangunan RB123 masih ekonomis dibanding harga pasaran?”

RB123 wants to educate customers and provide transparent market-based estimations.

This project enables RB123 to:
* Offer objective property price estimates
* Help clients make more confident financial decisions
* Demonstrate that RB123 construction costs are competitive
* Improve consultation workflows using a simple ML-powered web tool

The goal is to produce an accurate and explainable model along with a simple interactive web interface.

### **❓ Problem Statements**

How can we build an accurate machine learning model that predicts residential house prices in Bandung using only location and physical property features?

Supporting questions:

* Which machine learning model performs best on unseen data?

* What features most strongly influence house prices in Bandung?

### **🎯 Project Objectives**

This project aims to:

* Build an ML regression model for predicting Bandung house prices
* Identify key features affecting price (feature importance)
* Provide RB123 with a tool to compare construction costs vs. market prices



### **📊 Dataset**

The dataset was scraped from a property e-commerce website.

Features used:

* district – Area of the house
* sub_district – More detailed locality
* bedrooms – Number of bedrooms
* land_area – Land size (m²)
* building_area – Building size (m²)

Target variable:
* price – House price in Indonesian Rupiah (IDR)

### **Model Building**

We have built eleven (default) machine learning models to search for the best model candidates. The top candidates are models with the smallest error value. We can see that the RandomForestRegressor, LGBMRegressor, and GradientBoostingRegressor are the top performance models. The result can be seen below.

| Model ID | Model Name                 | MAPE_val | MAPE_test | MAE_val              | MAE_test             | RMSE_val             | RMSE_test            |
|----------|-----------------------------|----------|-----------|-----------------------|-----------------------|-----------------------|-----------------------|
| 3        | RandomForestRegressor       | -17.19   | 15.20     | -297,765,634.42       | 346,095,529.07        | -540,371,315.56       | 649,292,389.01        |
| 10       | LGBMRegressor               | -18.13   | 16.93     | -313,625,362.09       | 366,838,098.90        | -546,611,388.37       | 649,537,337.99        |
| 5        | GradientBoostingRegressor   | -20.49   | 19.31     | -321,223,349.76       | 383,994,787.33        | -542,756,039.67       | 650,894,916.15        |
| 2        | DecisionTreeRegressor       | -21.75   | 20.35     | -327,769,392.09       | 381,906,821.98        | -573,106,815.90       | 658,141,388.46        |
| 4        | AdaBoostRegressor           | -30.11   | 27.02     | -414,601,981.93       | 458,809,994.12        | -609,315,073.60       | 660,533,690.01        |
| 9        | CatBoostRegressor           | -19.05   | 18.56     | -320,166,814.36       | 371,404,519.40        | -563,204,999.94       | 666,694,214.85        |
| 1        | Lasso                       | -22.25   | 22.32     | -361,117,183.55       | 427,071,543.93        | -558,967,346.69       | 667,416,879.63        |
| 0        | Ridge                       | -22.55   | 22.46     | -361,177,113.74       | 427,240,130.27        | -558,481,740.06       | 667,743,299.47        |
| 7        | KNeighborsRegressor         | -17.90   | 18.07     | -303,789,897.86       | 378,306,515.59        | -526,501,815.47       | 693,164,209.52        |
| 6        | XGBRegressor                | -18.05   | 16.87     | -328,410,806.49       | 374,351,958.05        | -616,487,198.68       | 708,196,327.61        |
| 8        | SVR                         | -90.61   | 75.37     | -1,219,354,987.87     | 1,311,882,046.03      | -1,697,042,946.67     | 1,875,113,207.51      |

### **Hyperparameter Tuning**

After selecting those three models, we conducted hyperparameter tuning on them. Based on our results, the best performance model is the LGBM regressor (tuned) with the smallest MAPE and RMSE on the testing dataset. The result can be seen below.

| Model                       | RMSE Train   | RMSE Test   | MAPE Train | MAPE Test |
|-----------------------------|--------------|-------------|------------|-----------|
| **Random Forest Regressor (Tuned)**     | 532.080.695  | 644.888.857 | 18 %       | 17 %      |
| **Light GBM Regressor (Tuned)**        | 530,876,376  | 640,545,737 | 19 %       | 17 %      |
| **Gradient Boosting Regressor (Tuned)** | 544,173,380  | 656,156,979 | 18 %       | 16 %      |

### **Learning Curve**

<img width="920" height="428" alt="image" src="https://github.com/user-attachments/assets/d421af5c-1499-45e0-ad09-3481929dfd05" />

### **Feature importance**

<img width="954" height="299" alt="image" src="https://github.com/user-attachments/assets/8cc9fb49-6abf-4f36-b82a-65cb10db3656" />

### **Residual plot**

<img width="924" height="375" alt="image" src="https://github.com/user-attachments/assets/5897dec1-bc9a-403a-bd06-0d070942bd38" />

### **Model Performance on House Price Prediction**

The tuned LGBM model performed differently across different ranges of price. The model performed the best with the smallest error in the medium price range between IDR 1.5 million and IDR 3 million.

<img width="922" height="394" alt="image" src="https://github.com/user-attachments/assets/6fc24456-05ca-480e-aa94-153bb72a17b4" />


### **🚀Apps**

* The deployed apps can be seen here: [Bandung House predictor](https://app-house-prices-8fe4kxbfh4mghwrjexudzs.streamlit.app/)

![image](https://github.com/harishmuh/House-price-prediction-in-Bandung/blob/main/images/house%20prediction%20sample.PNG?raw=true)

### **Acknowledgement**
I would like to thank [RancangBangun123](https://rancangbangun123.com/) and [Reza Amansyah](https://github.com/RezaAmansyah) who were supporting this work.



