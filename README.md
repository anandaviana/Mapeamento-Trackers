# Mapeamento de Trackers em Usinas Fotovoltaicas

 ![Frame 1](https://github.com/user-attachments/assets/d6c34b36-020b-4cc9-957d-25d120c57479)

 ### Tecnologias e ferramentas
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg" width="15" height="15"/> Python
   &nbsp;&nbsp;&nbsp;
   <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/pandas/pandas-original.svg" width="15" height="15"/> Pandas
   &nbsp;&nbsp;&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vscode/vscode-original.svg" width="15" height="15" /> VS Code
    &nbsp;&nbsp;&nbsp;

## Resumo:
Nesse projeto desenvolvi um script para realizar o carregamento de informações de equipamentos de usinas solares em um arquivo 'xlsx' unificado, a ser usado como base pela contratante (empresa de monitoramento de ativos).

## Contexto:
Dado um arquivo base com uma lista de todos os trackers (TrackersId.xlsx), com nomenclatura padrão da contratante, e um conjunto de arquivos com informações de *Trackers, Strings e Inversores* fornecido pela empresa cliente da contratante, com padrão de nomenclatura distinto, a demanda consistia em agrupar em um novo arquivo apenas informações referentes a trackers e inversores, seguindo o padrão de nomenclatura da empresa de monitoramento.
Essa demanda surge por conta da divergência entre o projeto, a execução e as informações de mapeamento das usinas fotovoltaicas, algo bastante comum nesse mercado. Por isso, para um adequado gerenciamento da operação e manutenção das plantas, é necessário ter documentado as reais conexões existentes entre Tracker e Inversores, de modo que o sistema de monitoramento seja alimentado corretamente e possa funcionar de maneira eficaz. 

## Solução:
Como mencionado, havia divergência na nomenclatura dos Trackers entre os arquivos fornecidos pela contratante. Por isso, o primeiro passo foi identificar os caracteres divergentes e excluí-los do arquivo da empresa de monitoramento, que serviu como base. Feito isso, foi feita a verificação do padrão da nomenclatura resultante e aplicado tratamento onde se fez necessário. Com essa lista de nomes (ou Ids) de Trackers devidamente padronizada, criei um novo dataframe que receberia essa lista de Ids e seus respectivos Inversores, filtrados dos arquivos fornecidos pela empresa contratante. Para melhor organização, agrupei os inversores por tracker, de modo que cada linha do dataframe corresponde a um único Tracker, e um Tracker pode estar associado a mais de um Inversor. 


## Glossário: 
*String:* Conjunto de painéis solares conectados. <br>
*Tracker:* Motor que controla a inclinação de uma fileira de paineis (uma ou mais strings).<br>
*Inversor:* Recebe a energia das Strings (DC, corrente contínua) em AC (corrente alteranda). <br>
*STS*: Subdivisão de inversores conectados em um mesmo transformador. 

