# References — PyCaret + IBM Telco Customer Churn

## Ambiente escolhido para a aula

- Python: 3.11.x, 64-bit
- PyCaret: 3.3.2
- Pandas: 2.1.4
- NumPy: 1.26.4
- SciPy: 1.11.4
- Scikit-learn: 1.4.2
- Joblib: 1.3.2
- IPython Kernel: 6.29.5
- Jupyter: 1.0.0
- Matplotlib: 3.8.4
- Seaborn: 0.13.2

## Por que PyCaret 3.3.2?

A aula foi planejada usando a API clássica do PyCaret 3.x:

    setup()
    compare_models()
    create_model()
    tune_model()
    evaluate_model()
    predict_model()
    finalize_model()
    save_model()
    load_model()

O PyCaret 4.x possui uma API diferente e, no momento, versões 4.x aparecem como releases alpha no PyPI. Para uma aula didática baseada na API 3.x, vamos manter PyCaret 3.3.2.

## Fontes oficiais / referências

PyCaret — documentação:
https://pycaret.readthedocs.io/

PyCaret — API de Classification:
https://pycaret.readthedocs.io/en/stable/api/classification.html

PyCaret — PyPI 3.3.2:
https://pypi.org/project/pycaret/3.3.2/

PyCaret — releases:
https://github.com/pycaret/pycaret/releases

IBM — repositório do case Telco Customer Churn:
https://github.com/IBM/telco-customer-churn-on-icp4d

IBM — dataset Telco Customer Churn:
https://github.com/IBM/telco-customer-churn-on-icp4d/blob/master/data/Telco-Customer-Churn.csv

## Observação sobre o dataset

Vamos utilizar a versão clássica do dataset, com aproximadamente 7.043 registros e 21 colunas.

A variável que queremos prever é:

    Churn

Não vamos utilizar versões que contenham campos derivados como "Churn Score" para o treinamento, pois eles podem representar informação já produzida por outro modelo e introduzir leakage.


