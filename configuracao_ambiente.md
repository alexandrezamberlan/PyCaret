# Preparação do ambiente Python para a aula de PyCaret

Este guia mostra, de forma simples, como preparar o ambiente no Windows
usando Python 3.11, VS Code e Jupyter.

------------------------------------------------------------------------

## Abrir o terminal do VS Code

## 1. Permitir a execução de scripts do PowerShell

``` powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### O que faz?

Permite que o PowerShell execute scripts no seu usuário.

-   `Set-ExecutionPolicy` → altera a política de execução.
-   `RemoteSigned` → permite scripts locais e exige assinatura para
    alguns scripts baixados da internet.
-   `CurrentUser` → altera somente para o usuário atual.

------------------------------------------------------------------------

## 2. Instalar o Python 3.11

``` powershell
winget install --id Python.Python.3.11 --source winget
```

------------------------------------------------------------------------

## 3. Criar o ambiente virtual

``` powershell
py -3.11 -m venv .venv
```

### Por que usar um ambiente virtual?

Para manter as bibliotecas desta aula separadas de outros projetos do seu computador.

------------------------------------------------------------------------

## 4. Ativar o ambiente virtual

``` powershell
.\.venv\Scripts\Activate.ps1
```

### O que faz?

Ativa o ambiente virtual criado anteriormente.

Depois de ativado, o terminal normalmente mostra:

``` text
(.venv) PS C:\...\pycaret-ibm-churn-aula>
```

O `(.venv)` indica que o ambiente está ativo.

------------------------------------------------------------------------

## 5. Atualizar o pip

``` powershell
python -m pip install --upgrade pip
```
------------------------------------------------------------------------

## 6. Instalar as bibliotecas do projeto

``` powershell
pip install -r requirements.txt
```

### O que faz?

Instala todas as bibliotecas listadas no arquivo `requirements.txt`.

No nosso projeto, ele instala as versões definidas para a aula,
incluindo:

-   PyCaret
-   pandas
-   numpy
-   scikit-learn
-   Jupyter
-   ipykernel
-   matplotlib
-   seaborn

------------------------------------------------------------------------

# Configuração no VS Code

## 7. Selecionar o Kernel

Depois de abrir o arquivo `.ipynb` no VS Code:

1.  Procure a opção **Select Kernel**.
2.  Escolha o ambiente `.venv`.
3.  Confirme que ele está usando o Python 3.11.

O Kernel é o Python que será usado para executar as células do notebook.

### Como conferir?

Execute no notebook:

``` python
import sys

print(sys.version)
```

Deve aparecer uma versão começando com:

``` text
3.11
```

------------------------------------------------------------------------

## 8. Instalar as extensões do VS Code

No VS Code, abra a área de **Extensions** e instale:

### Python

Extensão oficial da Microsoft:

``` text
Python
```

### Jupyter

Extensão oficial da Microsoft:

``` text
Jupyter
```

Essas extensões permitem trabalhar com arquivos `.py` e notebooks
`.ipynb`.

------------------------------------------------------------------------

# Resumo

A sequência principal é:

``` powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

winget install --id Python.Python.3.11 --source winget

py -3.11 -m venv .venv

.\.venv\Scripts\Activate.ps1

python -m pip install --upgrade pip

pip install -r requirements.txt
```

Depois, no VS Code:

``` text
1. Abrir o projeto
2. Abrir o notebook .ipynb
3. Select Kernel
4. Selecionar o .venv (Python 3.11)
5. Instalar as extensões Python e Jupyter
6. Executar o notebook
```

## Verificação final

No terminal:

``` powershell
python --version
```

Deve mostrar:

``` text
Python 3.11.x
```

No notebook:

``` python
import pycaret

print(pycaret.__version__)
```

Deve mostrar:

``` text
3.3.2
```

Assim, o ambiente está pronto.
