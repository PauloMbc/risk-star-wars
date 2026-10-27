# Regras e roteiro de desenvolvimento — Risk Star Wars

Este documento distingue o que existe no protótipo do que continua planejado. O jogo é de estratégia territorial e não faz parte do RPG narrativo.

## 1. Ciclo de turno implementado

1. O jogador recebe reforços com base no território controlado e recebe um bônus se ainda controlar sua capital.
2. Créditos são arrecadados pela receita dos planetas possuídos.
3. O jogador posiciona reforços, pode contratar duas tropas com créditos e escolhe seus ataques.
4. Cada ataque resolve uma rodada de dados. O atacante pode rolar até três dados e o defensor até dois, limitado pelas tropas disponíveis.
5. Os dados são ordenados e comparados em pares. Um empate é vitória da defesa.
6. Ao conquistar um planeta, o atacante transfere tropas da origem para o território capturado.
7. Ao encerrar o turno, as duas facções rivais recebem reforços e realizam até quatro tentativas de ataque cada uma.
8. A campanha termina quando uma facção controla pelo menos 10 dos 16 planetas.

## 2. Facções implementadas

| Facção | Vantagem atual | Intenção estratégica |
|---|---|---|
| Ordem Jedi | +1 nos resultados de defesa | Resistência e controle |
| Império Sith | +1 nos resultados de ataque | Pressão ofensiva |
| Caçadores de Recompensas | Mercenários custam 3 créditos, em vez de 4 | Economia e flexibilidade |

Os modificadores são provisórios e precisam ser testados para evitar uma vantagem exagerada.

## 3. Planetas e território

Cada planeta possui proprietário, tropas, nível, receita econômica, descrição e rotas para outros planetas. As capitais iniciais são Coruscant (Jedi), Korriban (Sith) e Nal Hutta (Caçadores). Os outros territórios começam como propriedades das facções ou neutros, conforme a configuração inicial no código.

Os níveis I, II e III são, nesta versão, principalmente informativos. As regras futuras devem tornar o nível relevante para defesa, receita, eventos e exigências de conquista.

## 4. Decisões de projeto a validar

- **Vitória:** o limite de 10 planetas é um objetivo de teste para evitar partidas longas. Deve ser comparado com vitória por capitais, eliminação de facções ou domínio total.
- **Economia:** receita e contratação são simples de propósito. Deve-se medir se os créditos ajudam as escolhas ou tornam o reforço comum irrelevante.
- **IA:** os rivais usam uma estratégia heurística básica. Não é uma IA competitiva nem prova de equilíbrio.
- **Combate:** os modificadores de facção e limites de perdas precisam de testes automatizados e simulações.
- **Diplomacia:** não está implementada nesta versão. A regra conceitual prevê negociação pacífica ou intimidação, consumo de créditos/influência, lealdade planetária e risco de rebelião.
- **Espaço e superfície:** batalhas espaciais e invasões em planetas de alto escalão ainda não existem no código.

## 5. Roteiro recomendado

### Fase 1 — Base jogável
- [x] Escolha de facção.
- [x] Mapa territorial interativo.
- [x] Rotas e seleção de alvo adjacente.
- [x] Reforços, créditos e mercenários.
- [x] Combate por dados e captura de território.
- [x] Turnos de duas facções rivais controladas por IA.
- [x] Condição de vitória e registro de eventos.
- [ ] Corrigir e validar os casos extremos de combate com testes automatizados.
- [ ] Separar a lógica de jogo da interface para facilitar evolução.
- [ ] Persistir a campanha em armazenamento local.

### Fase 2 — Regras territoriais mais profundas
- [ ] Levar nível planetário para dentro das regras de combate e defesa.
- [ ] Implementar lealdade, instabilidade, rebeliões e eventos planetários.
- [ ] Implementar movimento estratégico e transferência de tropas sem ataque.
- [ ] Ajustar economia, receita e limites de recrutamento com simulações.

### Fase 3 — Heróis e espaço
- [ ] Heróis/comandantes por facção com habilidades distintas.
- [ ] Transporte de líderes por naves entre sistemas.
- [ ] Combate espacial como etapa quando um planeta exigir domínio do espaço.
- [ ] Classes de nave e custo de manutenção.

### Fase 4 — Diplomacia e contratos
- [ ] Negociação pacífica e intimidação com probabilidade explícita.
- [ ] Créditos e influência como recursos separados.
- [ ] Lealdade do planeta e risco de rebelião após acordo.
- [ ] Contratos de recompensa, espionagem e informação de mapa.

### Fase 5 — Qualidade e publicação
- [ ] Testes de regras e testes de interface.
- [ ] Balanceamento de facções, partidas curtas e partidas longas.
- [ ] Acessibilidade, telas pequenas e feedback visual de combate.
- [ ] Salvamento, reinício de campanha e opções de dificuldade.
- [ ] Publicar pelo GitHub Pages quando o protótipo estiver validado.

## 6. Critérios mínimos para considerar a base estável

1. Um ataque só pode ocorrer entre planetas conectados e pertencentes a lados diferentes.
2. Nenhuma regra pode deixar uma origem sem tropas.
3. Recursos não podem ficar negativos.
4. Não é possível agir depois de a partida terminar.
5. Cada captura altera corretamente controle, contagem de territórios e condição de vitória.
6. A IA não pode executar turnos infinitos nem atacar com uma única tropa.
7. Recomeçar uma campanha restaura os proprietários, tropas, recursos e registros iniciais.
