# Neural Networks approach: How well performs a Long Short-Term Memory (LSTM) model to predict inflation in Chile?

In this repository I show the performance of LSTM neurons for predicting the CPI inflation in Chile for annualized monthly data. I make use of the Diebold-Mariano test in order to measure the effectiveness of the RNN models, and I considered the Central Bank of Chile Economic Expectation Surveys as the opposite model. Univariate RNN models are not sufficient to outperform the Economic Expectation Surveys forecast accuracy for 1-month and 1-year horizons. However, Multivariate RNN models (that is to say, considering some of the main macroeconomic variables of Chile) statistically demonstrates they are as good as Economic Expectation Surveys forecasts.

All the data were extracted directly from the Central Bank of Chile Databases, and it all comprises from 1921m1 to 2021m6 for the univariate models, and from 1996m1 to 2021m5 for the multivariate models.

## Repository Structure

The repository is structured as follows:

- ```univariate_models```: contains the univariate RNN models.
  - ```rnn_selection_1_month_ahead.ipynb```: contains the selection of the hyper-parameters of the neural network that minimizes the Mean Squared Error for the 1-month horizon.
  - ```rnn_selection_11_months_ahead.ipynb```: contains the selection of the hyper-parameters of the neural network that minimizes the Mean Squared Error for the 1-year horizon.
  - ```hyper_parameters_optimization.ipynb```: stores the hyper-parameters of 960 models, with their respective Mean Squared Error for the 1-month horizon.
  - ```hyper_parameter_optimization_11_months.ipynb```: stores the hyper-parameters of 960 models, with their respective Mean Squared Error for the 1-year horizon.
  - ```lstm_vs_eee_11_months.ipynb```: performs the in-sample forecasting of the best model found in ```rnn_selection_11_months_ahead.ipynb``` in order to compare it with the Economic Expectation Surveys.
- ```multivariate_models```:
  - ```mv_rnn_selection_11_months_ahead.ipynb```: contains the selection of the hyper-parameters of the neural network that minimizes the Mean Squared Error for the 1-year horizon.
  - ```mv_hp_opt_11_months```: stores the hyper-parameters of 960 models, with their respective Mean Squared Error for the 1-year horizon.
  - ```mv_lstm_vs_eee_11_months.ipynb```: performs the in-sample forecasting of the best model found in ```mv_rnn_selection_11_months_ahead.ipynb``` in order to compare it with the Economic Expectation Surveys.
- ```requirements.txt```: is the executable file which contains the required ```python``` libraries in order to execute the notebooks.
