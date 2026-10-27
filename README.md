# Risk Star Wars — Conquista Galáctica

Protótipo web jogável de estratégia inspirado nas regras de conquista territorial descritas no projeto. Este jogo é separado do projeto de RPG narrativo.

## Abrir o jogo

A aplicação não precisa de Node.js, instalação de pacotes ou compilação.

- Abra `index.html` diretamente no navegador; ou
- Ative o GitHub Pages em **Settings → Pages → Deploy from a branch**, selecione a branch `main` e a pasta `/ (root)`. Depois, abra o endereço publicado pelo GitHub.

## O que já funciona nesta primeira versão

- Escolher entre Ordem Jedi, Império Sith e Caçadores de Recompensas.
- Mapa interativo com 16 planetas, rotas e territórios neutros.
- Selecionar origem e alvo conectado.
- Combates com rolagem de dados e perdas de tropas.
- Reforçar territórios e contratar mercenários usando créditos.
- Turnos de duas facções controladas por IA.
- Capital, níveis planetários, receita econômica e meta de vitória por domínio de 10 planetas.
- Registro dos últimos acontecimentos e layout responsivo para celular.

## Identidade de cada facção

- **Ordem Jedi:** recebe +1 nos resultados de defesa.
- **Império Sith:** recebe +1 nos resultados de ataque.
- **Caçadores de Recompensas:** contratam mercenários por 3 créditos, em vez de 4.

## Como jogar

1. Escolha uma facção e inicie a campanha.
2. Clique em um planeta seu para selecioná-lo como origem.
3. Clique em um planeta vizinho conectado por uma linha para definir o alvo.
4. Use **Reforçar planeta** para gastar reforços ou **Contratar tropas** para usar créditos.
5. Clique em **Atacar planeta selecionado** para resolver uma rodada de combate. Em empate, a defesa vence.
6. Encerre o turno para permitir que as duas facções rivais ajam.
7. Controle 10 planetas para vencer.

## Estrutura atual

```text
risk-star-wars/
├── index.html        # Interface, mapa, regras e lógica da partida
├── README.md         # Este guia
└── docs/
    └── ROADMAP.md    # Regras atuais e plano de desenvolvimento
```

## Limitações conhecidas

Esta é uma primeira versão funcional, não o jogo completo descrito no conceito. Ainda faltam diplomacia negociável, heróis e comandantes transportáveis, combate espacial, contratos de recompensa, espionagem, eventos, salvamento de campanha, testes automatizados e balanceamento por partidas repetidas.

As regras e valores são parâmetros iniciais para teste, não números finais de balanceamento. O progresso não é salvo depois que a página é fechada.

## Próximas etapas

Consulte [docs/ROADMAP.md](docs/ROADMAP.md) para a sequência de desenvolvimento.
