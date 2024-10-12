
# Group project S.N Bose Research Internship Under Dr. Banani Basu

# Stock-Predictor-V4

![stockpredictor ai logo](https://user-images.githubusercontent.com/53996451/224323224-3ec1cd20-747c-42ad-9fb1-ba6e0ecb358b.png)

> The Stock-Predictor-V4 Project has undoubtedly reached its full potential, and at this stage, third-party pull requests represent the sole avenue for introducing new features and functionalities. Unfortunately, due to my limited expertise in prediction logic, I had to remove it entirely from the update cycle. Embracing the contributions of skilled developers through pull requests is now the most promising way to breathe fresh life into the project and ensure its continued growth and relevance.

---

## Now On Colab! [![Open SPV4 In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/lex-hue/Stock-Predictor-V4/blob/main/SPV4.ipynb)

---
# Content Table

- [Stock-Predictor-V4](#stock-predictor-v4)
  - [1a. Installation](#1a-installation)
  - [1b. Updating the Repository](#1b-updating-the-repository)
  - [2. Data Preparation](#2-data-preparation)
  - [3. Training the LSTM RL Model](#3-training-the-lstm-rl-model)
  - [4. Evaluating the Model](#4-evaluating-the-model)
  - [5. Fine Tuning the LSTM RL Model](#5-fine-tuning-the-lstm-rl-model)
  - 6. Utilizing the Model for Stock Market Prediction (Is in Constuction, dont use it!)
  - [7. Comparing the predicted values with the actual values after the 30-day period.](#7-comparing-the-predicted-values-with-the-actual-values-after-the-30-day-period)

---

**Recommended PC Specifications for Stock-Predictor-V4:**

- GPU VRAM: 4 GB
- RAM: 6 GB (when equipped with a GPU)
- RAM: 10 GB (without a GPU)
- Supported Operating Systems: Linux, Mac, or Windows

If your PC meets at least 70% of these recommendations, it should perform well during the training process. If your specs fall below this threshold, consider running the program on [Colab](https://colab.research.google.com/github/lex-hue/Stock-Predictor-V4/blob/main/SPV4.ipynb) (highly recommended) or on your local machine (May take long).



## 1a. Installation
```
git clone https://github.com/lex-hue/Stock-Predictor-V4.git
cd Stock-Predictor-V4
python SPV4.py --install
```

---

### 1b. Updating the Repository
```
python SPV4.py --update
python SPV4.py --install
```
**You must retrain your Models so that the new Code Supports it*

---

## 2. Data Preparation
To prepare the data for stock prediction, you can follow either of the following options:
1. Run the `SPV4.py` script by executing `python SPV4.py --prepare_data` and type in the Ticker Symbol youd like to Preprocess (For Example BTC-USB, AAPL or so).

Upon completion of these steps, your Preprocessed stock data will contain indicators that enhance the reliability of predictions.

---

## 3. Training the LSTM RL Model

To train the LSTM RL Model with the `data.csv` file that was generated by the 2. Step, execute the following:

```
python SPV4.py --train
```
After running this command, the LSTM RL model will start training with the data in the data.csv file.

---

## 4. Evaluating the Model
To evaluate the trained model, execute the following:

```
python SPV4.py --eval
```

After running this command, the root mean squared error (RMSE), the MAPE and Total Rewards will be plotted.

---

## 5. Fine Tuning the LSTM RL Model

To fine tune the model, execute the following:
```
python SPV4.py --fine_tune
```
Before starting the fine-tuning process for the LSTM RL model, the script will now ask you to specify your desired reward threshold. It is recommended to set the threshold at 0.9.

It is recommended to maintain hydration by drinking water while waiting for the fine-tuning process to complete, as this may take a while. Once the fine-tuning is done, attempt to run the script with a single loop. If the script doesn't loop once initially, keep rerunning it until it completes at least one loop. If the script consistently produces the same result without any improvement, please interrupt it by pressing CTRL + C, answer "yes" to the prompt, and rerun the script.

After the fine-tuning process is fully complete, it is highly recommended to re-evaluate the model's performance.

---

### Predicting into the Future. Will maybe come back from an third-party Pull Request...

---

## 7. Comparing the predicted values with the actual values after the 30-day period.

If you've reached the end of the 30-day predicted period and you're curious about the accuracy of the model, then the script can help you. To compare the data, you need to update the CSV file you selected in Step 2.

After that, run the following command in your terminal:
```
python SPV4.py --compare
```

This will compare the predicted data with the actual data. You may regret some of the decisions you made and wonder why you didn't trust the model.
