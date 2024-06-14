# Real Estate Price Prediction with Machine Learning

## Source Data and Statistics

- **Source**: Data from Yandex.Realty classified containing real estate listings for apartments in St. Petersburg and Leningrad Oblast from 2016 till the middle of August 2018.
- **Objective**: Analyze the dataset and build a machine learning model to predict real estate prices.

### Statistics
- **Median and Mean Prices**: Calculated median and mean sell and rent prices in St. Petersburg.
- **Outliers Detection**: Identified and removed outliers - apartments with unusually low or high prices.
- **Price per Square Meter**: Determined houses with the cheapest and most expensive prices per square meter.
- **Rent Offers Analysis**: Analyzed the number of rent offers with commissions and identified the most popular commission rate.

## Model and Framework

- **Framework**: Utilized scikit-learn, a popular machine learning library in Python.
- **Model**: Implemented a Random Forest Regressor for price prediction.
- **Hyperparameters**:
  - `n_estimators`: [10, 20, 30, 50, 100, 200]
  - `bootstrap`: [True, False]
  - `max_depth`: [5, 10, 15]
  - `min_samples_split`: [2, 3, 4]
  - `max_features`: [1, 2, 3]

 ## Installation and Running Instructions

1. **Clone the Repository**: `git clone https://github.com/bltvvv/e2e_project`
2. **Setup Virtual Environment**: `python3 -m venv venv`
3. **Activate Virtual Environment**:
   - On macOS/Linux: `source venv/bin/activate`(from my code)
   - On Windows: `venv\Scripts\activate`
4. **Install Dependencies**: `pip install -r requirements.txt`
5. **Run the Application**: `python app.py`

## Dockerfile

```dockerfile
FROM ubuntu:22.04

MAINTAINER st119492

RUN apt-get update -y

COPY . /opt/gsom_predictor

WORKDIR /opt/gsom_predictor

RUN apt install -y python3-pip

RUN pip3 install -r requirements.txt

CMD python3 app.py
```

## Requirements

```
blinker==1.8.2

click==8.1.7

Flask==3.0.3

itsdangerous==2.2.0

Jinja2==3.1.4

joblib==1.4.2

MarkupSafe==2.1.5

numpy==1.26.4

scikit-learn==1.2.2

scipy==1.13.1

threadpoolctl==3.5.0

Werkzeug==3.0.3
```


## Opening Port on Remote VM

To open the port on your remote VM, you need to configure the firewall settings to allow inbound traffic on port 7778.

## Running the Application with Docker

1. **Build Docker Image**: `docker build -t st119492/gsom_e2e:v.0.4 .`
2. **Run Docker Container**: `docker run --network host -d st119492/gsom_e2e:v.0.4`

The application will be accessible at `http://<your_vm_ip>:7778`. (will be later)



