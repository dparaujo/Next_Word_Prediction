# Previsão da Próxima Palavra com BERT (acadêmico)

Caio Pinho e David Araújo - Deep Learning

# Descrição

Este repositório contém um script desenvolvido utilizando a linguagem de programação Python para fazer a previsão da próxima palavra no idioma em português usando o modelo pré-treinado BERT e treinado na língua portuguesa. Esse script pode ser executado utilizando o Google Colab ou terminal linux com as devidas configurações descritas abaixo. O código do script está no arquivo nomeado: `Next_Word_Prediction_with_Transformers.ipynb`.

O modelo BERTimbau disponibilizado pela a Neuralmind, segue o link do github para mais informações: https://github.com/neuralmind-ai/portuguese-bert ou https://neuralmind.ai/sobre/, possui dois modelos pré-treinados BERT-Base e BERT-Large Cased e foram treinadas no BrWaC (Brazilian Web as Corpus). O BrWaC é um grande corpus português, por 1.000.000 de palavras, usando máscara de palavras inteiras.

---

# Instalação das dependências

O script com o modelo pré-treinado é baseado na biblioteca HuggingFace Transformers. E para o correto funcionamento das dependências do script será necessário a instalação da biblioteca com o seguinte comando, caso utilize o Google Colab: `!pip3 install transformers`

Se for usar o um terminal linux, dentro da sua virtual env pode ser executado o comando: `pip3 install transformers`

# Instalação Preliminar

Recomendamos criar um ambiente virtual com python 3.6+ e PyTorch.

# Dataset

No script desenvolvido inclui o diretório do conjunto de dados para modelos pré-processados como é o caso do modelo BERT. O conjunto de dados que usamos em nossos experimentos disponibilizado pela (Neuralmind). Consulte o link: https://github.com/neuralmind-ai/portuguese-bert para obter mais detalhes.

# Exemplo usando PyTorch

Segue abaixo um trecho de código que foi utilizado no desenvolvimento do script. Foi criado um modelo e um tokenizador baseados na bilbioteca `Transformers` e utilizada a base de dados em português da `neuralmind`.

```
from transformers import AutoModel, AutoTokenizer

# Usando o modelo da comunidade
# Base BERT
tokenizer = AutoTokenizer.from_pretrained('neuralmind/bert-base-portuguese-cased')
model = AutoModel.from_pretrained('neuralmind/bert-base-portuguese-cased')

# BERT Large
tokenizer = AutoTokenizer.from_pretrained('neuralmind/bert-large-portuguese-cased')
model = AutoModel.from_pretrained('neuralmind/bert-large-portuguese-cased')
```

# Execução do Script (fazendo a previsão da próxima palavra)

Após realizar a instalação das dependências, pode executar cada célula do Google Colab seguindo a ordem das células. Na variável `top_k` pode ser definida a quantidade de palavras resutantes para previsões.

Depois de rodar as células, ou seja, executar as funções em python até a função: get_all_predictions, será necessário fazer a entrada de dados (textos em portugûes). Essa entrada de dados é uma frase curta para o script fazer a previsão da próxima palavra levando em consideração a frase informada na variável: `input_text`

Depois da entrada de dados e execução da célula do Colab que cotém a variável `input_text`, será apresentada as possíveis previsões das palavras para completar a frase digitada anteriormente. Nesse caso os resultados será uma lista de palavras que poderão completar a frase. Dessa forma, é realizada a previsão da próxima palavra.

# Relatório Técnico

Para mais informações a respeito do script desenvolvimento foi feito um relatório técnico com mais detalhes que apresentados os resultados obtidos.

O relatório também encontra-se neste repositório, está no formato .pdf podendo ser baixado direto do repositótio e nomeado: `Relatório - Predição da Próxima Palavra em Português usando Transformers.pdf`

# Referências

[1] https://github.com/huggingface/transformers

[2] https://github.com/neuralmind-ai/portuguese-bert

[3] https://github.com/google-research/bert

[4] https://arxiv.org/pdf/1810.04805.pdf
