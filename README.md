# Final_Project_MBA_DSA

### I. Apresentação

Este repositório foi criado com o objetivo de documentar o processo de criação da base de dados utilizada no projeto final do curso de MBA em Data Science e Analytics. Aqui você encontrará informações detalhadas sobre os passos tomados, as técnicas utilizadas e os recursos empregados na construção da base de dados. 

### II. Motivação do trabalho

Contribuir com a eficiência do sistema de mobilidade urbana de Belo Horizonte a partir da análise e visualização dos registros de acidentes de trânsito na região central de Belo Horizonte. 

### III. Coleta, integração e processamento dos dados

Os dados de acidentes utilizados neste trabalho foram obtidos a partir de duas fontes principais: as planilhas de descrição geral dos acidentes de trânsito e as planilhas de descrição dos veículos envolvidos nos acidentes de trânsito obtidos através do portal de dados abertos da Prefeitura de Belo Horizonte (PBH) disponível no endereço eletrônico: https://dados.pbh.gov.br.

Inicialmente, foi realizada a compilação das planilhas de descrição geral dos acidentes de trânsito referentes aos anos de 2017, 2018 e 2019. Essa etapa resultou em um dataframe com um total de 37.241 observações. Em seguida, foi aplicado um filtro nos dados para selecionar apenas as ocorrências registradas na região central de Belo Horizonte, o que reduziu o conjunto de dados para 1634 observações.

Posteriormente, foi feita a compilação das planilhas de descrição dos veículos envolvidos em acidentes de trânsito. Desse dataframe, composto por 67.614 observações, foram obtidas as quantidades de veículos envolvidos por tipo (bicicleta, motocicleta, automóvel, caminhão e ônibus) em cada ocorrência registrada. Essas informações foram acrescentadas ao dataframe de descrição geral dos acidentes, utilizando o número do boletim como identificador. Para garantir a consistência dos dados, foram eliminados os registros incompletos. Esse processo resultou em um dataframe final de acidentes com 1627 observações. 

Os dados meteorológicos utilizados neste estudo incluem informações de precipitação (em milímetros) registradas em intervalos horários ao longo de todos os dias dos anos de 2017, 2018 e 2019. Essas informações foram incorporadas ao dataframe de acidentes, utilizando a hora como identificador para a correspondência dos dados meteorológicos com os registros de acidentes.

Os dados de localização, obtidos através de um arquivo shapefile da malha viária de Belo Horizonte, passaram por um pré-processamento no qual foram identificadas a localização exata de todos os pontos de cruzamentos da rede viária do centro da cidade. Com os pontos de cruzamento definidos, foi possível classificar cada registro de acidente com base em suas coordenadas geográficas. Para essa classificação, foi considerado como ocorrência em cruzamento todos os acidentes localizados até 15 metros de distância dos pontos de cruzamento pré-definidos.

Todos os processos e considerações envolvidas nas etapas de coleta, integração e processamento dos dados foram realizados utilizando a linguagem de programação Python.
