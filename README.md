# User Behavior Analysis with Machine Learning

This project uses machine learning to classify user behavior based on mobile usage patterns. The goal is to demonstrate the entire machine learning lifecycle, including model training, saving the model, configuration management, and integration into a DevOps pipeline using Jenkins, Docker, and AWS.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Model Details](#model-details)
- [DevOps Pipeline](#devops-pipeline)
- [Contributing](#contributing)
- [License](#license)

---

## Project Overview

The User Behavior Analysis project aims to classify users into behavior classes based on their mobile usage data. The dataset consists of features like device model, usage time, battery drain, data usage, and more. A **RandomForestClassifier** is used along with **Principal Component Analysis (PCA)** for dimensionality reduction.

Key functionalities:
- Load and preprocess the user behavior dataset.
- Apply PCA for feature reduction.
- Train a Random Forest model.
- Save the trained model and configuration to files (`model.pkl` and `config.yaml`).
- Integrate the model with Jenkins for testing, Docker for containerization, and AWS for deployment.

---

## Technologies Used

- **Python 3** – Main programming language.
- **scikit-learn** – For training the machine learning model.
- **pandas** – For data manipulation.
- **yaml** – For configuration management.
- **pickle** – For saving the trained model.
- **Jenkins** – For continuous integration and testing.
- **Docker** – For containerization of the application.
- **AWS** – For deployment.

---

## Installation

Follow these steps to set up the project on your local machine or in a cloud environment like Google Colab.

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/user-behavior-analysis.git
    cd user-behavior-analysis
    ```

2. Install required Python libraries:
    ```bash
    pip install -r requirements.txt
    ```

---

## Usage

1. **Train the Model**: To train the model and save it along with the configuration, run `train.py`:
    ```bash
    python train.py
    ```

    This will:
    - Load and preprocess the user behavior dataset.
    - Apply PCA for dimensionality reduction.
    - Train the Random Forest model.
    - Save the model to `model.pkl`.
    - Save the configuration to `config.yaml`.

2. **Test the Model**: To test the model or evaluate the performance, run the `test_model.py` script:
    ```bash
    python test_model.py
    ```

---

## Model Details

The machine learning model used is a **RandomForestClassifier**. The model is trained on a dataset consisting of user behavior features like app usage time, screen on time, battery drain, and more.

- **Model Parameters**:
    - `n_estimators=100` (Number of trees in the forest)
    - `max_depth=5` (Maximum depth of the trees)
    - `random_state=42` (Seed for reproducibility)

The model is evaluated on accuracy, which is printed after the evaluation.

---

## DevOps Pipeline

This project integrates with the following DevOps tools:

1. **Jenkins**: Automates testing and triggers model training whenever code changes are pushed.
2. **Docker**: Containerizes the application for consistency across different environments.
3. **AWS**: Deploys the Dockerized application to AWS EC2 or Elastic Beanstalk for cloud-based production.

**Steps for Jenkins integration**:
- Set up Jenkins pipeline to automatically test and trigger the training process.

**Steps for Docker containerization**:
- Create a Dockerfile for building a container image.
- Build the container with `docker build -t user-behavior-analysis .`.
- Push the container to Docker Hub or deploy directly to AWS.

**Steps for AWS Deployment**:
- Deploy the Docker container to an EC2 instance or Elastic Beanstalk environment.

---

## Contributing

Contributions are welcome! To contribute to this project:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit them (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a pull request with a description of your changes.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


