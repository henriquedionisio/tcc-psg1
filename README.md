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
  - pd4web é como se fosse um tradutor. É como se fosse o Audience rodando na web.
  - Duas alternativas: adaptar pd4web para poder receber áudio pronto. Ou adaptar Audience para gerir o player. 


próximos passos:
- baixar ambos os repos (vsat e pd4web) e tentar fazer o merge dos dois.
  - usar arquivo ambisonics (pegar da nuvem - local pode suar baixado, web da nuvem)

  - pegar patch do professor
    - ele vai criar uma versao 3 pra receber um arquivo de audio
    - hoje os patches (v1 e v2) estao no repositorio vsat-audience na pasta audios
- eu sou fã de deixar o AFrame só pra fornecer as coordenadas, nao tocar o audio através dele. Continuar nativo no html assim como o pd4web faz.
- pedir ajuda pra compilar tudo e pedir arquivo .pd para teste

<img width="1222" height="696" alt="image" src="https://github.com/user-attachments/assets/248aab58-6177-41f9-aff3-6e11c8cfb96d" />

<img width="1239" height="694" alt="image" src="https://github.com/user-attachments/assets/3990eb37-b8cb-443d-b327-a0f123f5ef2b" />
