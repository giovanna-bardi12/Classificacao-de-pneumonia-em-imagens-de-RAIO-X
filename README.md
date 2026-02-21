# Classificação de Pneumonia em imagens de Raio-X

**Atenção:** Não foi possível subir os artefatos do modelo diretamente no Github, logo o arquivo está disponibilizado neste drive:

https://drive.google.com/drive/folders/1_jrPov9arOTtuBanH2kaYafki9-56bq3?usp=sharing

Este repositório contém a documentação e o código-fonte para a solução do desafio de Visão Computacional focado no diagnóstico de pneumonia em imagens de Raio-X. O modelo foi desenvolvido utilizando uma Rede Neural Convolucional (CNN).

## Organização do código

- `projetoLigiaPS.ipynb`: notebook principal contendo o pipeline completo (análise, pré-processamento, configuração da arquitetura da rede, treinamento e visualização de curvas Loss/AUC).
- `minha_submissao.csv`: exemplo da saída final formatada nos padrões exigidos pela plataforma.
- `requirements.txt`: lista de dependências estruturada para garantir a reprodutibilidade do ambiente.
- `melhor_modelo.h5`: artefato do Modelo, disponível no link do drive acima.

## Reprodutibilidade e pré-requisitos

Para garantir o funcionamento correto, recomenda-se a execução via Google Colab.

1. Clone este repositório.
2. Instale as dependências

```bash
pip install -r requirements.txt
```

1. Faça o Donwload do dataset:
    1. Link: https://www.kaggle.com/datasets/tolgadincer/labeled-chest-xray-images

## Execução do código e geração da submissão

### 1. Treinamento

Caso deseje reproduzir o treinamento do modelo:

- Abra o arquivo `projetoLigiaPS.ipynb`  e execute as células sequencialmente. O pipeline aplicará o pré-processamento de imagens e o cálculo dos pesos da classe.
- Ao fim do treinamento, o artefato `melhor_modelo.h5` será gerado localmente e os gráficos de validação serão plotados.

### 2. Inferência e Geração do CSV

Para gerar o arquivo oficial de submissão:

- Vá até a seção de inferência no final do notebook.
- Certifique-se de que o modelo treinado está carregado via `load_model`.
- Execute o bloco de inferência. O script processará individualmente as imagens de teste, extraindo a probabilidade e convertendo para as classes binárias (0 ou 1).
- O código exportará automaticamente o arquivo `minha_submissao.csv` na mesma pasta.

### 3. Submissão na Plataforma Kaggle

- Acesse a página oficial da competição no site do Kaggle. (https://www.kaggle.com/competitions/ligia-compviz/data)
- Entre na competição caso não esteja inscrito.
- Clique no botão Submit Predictions.
- Na área de upload, arraste e solte o arquivo `minha_submissao.csv` que foi gerado no passo anterior.
- Clique em submit para que a plataforma calcule o score da submissão.
