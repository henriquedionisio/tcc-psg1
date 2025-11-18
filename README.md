# tcc-psg1
> Vídeo de apresentação: https://drive.google.com/file/d/1x2mFYqSA2o2w_hZxuk2Sb9rnMDpkHj8e/view?usp=sharing

## Dúvidas:
Qual é a parte entregável para o projeto de PSG I? será estendido para PSG II?
- Será difícil entregar integração pronta no final de novembro (30/11 às 23h59)
- É possível particionar a entrega em dois semestres? Sendo essa primeira entrega um documento mediano com o que foi aprendido/feito.
- Se for preciso entregar um executável, não será possível pra entregar com pd4web, somente com o A-Frame (pois já existe biblioteca que roda Ambisonics direto no A-Frame)

## TO-DO
- [X] Criar repositório com nome de TCC e compartilhar com o professor
- [ ] Ler documentações do Github (Readme do VSAT + /main/docs) 
- [ ] Evoluir o diagrama de fluxo, está muito simples, arquitetura do software (heroku, bibliotecas, etc.) - A Frame
- [ ] Tentar rodar na máquina o projeto
- [ ] Criar cópia da documentação de novo e montar documento de andamento (documento de trabalho/andamento/diário de bordo), adicionando tabelas/figuras
- [ ] Unir referências e referências bibliográficas
  - Ordem: ou de aparecimento (chamadas numéricas) ou em ordem alfabética (autor/ano)
  - Citar no texto 


### Apontamentos reunião presencial (04/11):
Diagrama de blocos do sistema: como é a arquitetura geral?
- VSAT: https://github.com/LATM-USP/vsat_audience
- VSAT antigo: https://ancient-sierra-54813.herokuapp.com
- pd4web: https://github.com/charlesneimog/pd4web/blob/main/README.md
- Audience: fornecedor dos áudios em Ambisonics
- Heroku: hospeda site
- A-Frame: engine gráfica
- Magic: autenticação
- Codenary: serviço de nuvem que guarda imagens/sons
- Banco de dados: Docker - base de dados que salva histórias/textos
- 4 canais de áudio para o VSAT Audience

### Apontamentos reunião presencial (18/11):
- Discussão da integração pd4web com Audience e VSAT:
  - Avaliação da viabilidade de implementar isso.
  - Utilização de Container para reduzir ao máximo a latencia entre processamento de áudio pelo Audience e leitura pelo VSAT.
  - Retorno de áudio atualizado a todo tempo pelo Audience e retornado para o VSAT.
  - Browser tem muitas camadas de segurança que pode afetar a viabilidade da solução imaginada - limitação da API de áudio da web, que só aceita microfone ou áudio pronto: https://developer.mozilla.org/pt-BR/docs/Web/API/Web_Audio_API.
  - Comentamos sobre a viabilidade de usar streaming. Precisa ver se AFrame tem suporte a esse tipo de renderização de áudio: https://aframe.io/.
  - Outros links da reunião:
    - https://charlesneimog.github.io/pd4web/js/js/
    - https://www.researchgate.net/publication/395664963_Enabling_Interactive_Music_Performance_through_Web_Browsers_for_non-Programmers
  - Streaming e Patches. Patch vem de conexão, é o arquivo do PD, 
  - Planejamos fazer uma história de teste no VSAT.
  - pd4web não nasceu pra converter esse som pra web?
  - pd != pd4web. Audience é um "plugin" para pd. Uma ferramenta que usa pd.

