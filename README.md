# 🚎 Simulador de Linha Automatizada — Carga e Descarga (AGV)

Simulação interativa, 100% em HTML/CSS/JS, de um veículo guiado automatizado (AGV) operando em uma linha de produção fictícia, com coleta de matéria-prima e entrega em pontos de embalagem. Criado para uso em workshops de automação e logística industrial.

## 🔘 Motivação

Conceitos de logística automatizada — AGVs, trilhos guiados, rotas de coleta e entrega, sincronismo entre estações — costumam ser explicados apenas com slides estáticos ou vídeos institucionais de terceiros. Isso funciona para uma apresentação passiva, mas não para um workshop, onde o objetivo é que o participante **manipule o sistema, veja a consequência imediata das escolhas** e associe teoria a comportamento.

Este projeto nasceu dessa lacuna: um ambiente leve, sem instalação, sem backend e sem dependências pesadas, que qualquer participante consiga abrir em um navegador — no notebook, no celular ou projetado na sala — e operar em minutos. A ideia central é tornar tangível um conceito que normalmente é só descrito:

> "O AGV se move sobre um trilho fixo. Você escolhe de onde ele pega a carga e para onde ele leva. A rota usada fica visível. Cada decisão tem custo (distância, tempo) e pode cumprir um objetivo (desafio)."

Três decisões de design vieram diretamente dessa motivação:

1. **Rota sempre explícita.** Em vez de o AGV "teleportar" entre estações, ele percorre um trilho real (espinha + desvios), e o trecho utilizado acende visualmente. Isso reforça a lógica de um sistema físico de automação, onde a trajetória importa tanto quanto o destino.
2. **Zero fricção de acesso.** Um único arquivo `.html`, sem build, sem servidor, sem instalação de pacotes. Roda offline (exceto a fonte tipográfica, carregada via Google Fonts) em qualquer navegador moderno — pré-requisito para um workshop onde nem todo participante terá o mesmo ambiente técnico.
3. **Aprendizado por objetivo, não por exploração livre.** A adição dos desafios transforma a simulação de um brinquedo exploratório em uma atividade com métrica de sucesso, o que facilita a condução do workshop pelo facilitador e dá aos participantes um critério claro de "consegui" ou "não consegui".

## 🔘 O que a simulação representa

- **Estações de coleta (P1, P2, P3):** pontos de origem de matéria-prima, à esquerda da planta.
- **Estações de entrega (D1, D2, D3):** pontos de destino/embalagem, à direita da planta.
- **Trilho fixo:** estrutura em formato de espinha — dois eixos verticais (um de cada lado) ligados por um corredor horizontal central — pela qual o AGV necessariamente transita. Não existe atalho fora do trilho, propositalmente, para reforçar a ideia de infraestrutura fixa de automação.
- **AGV:** veículo único, que parte de uma posição de base, cumpre um ciclo completo (ida, coleta, retorno ao eixo, travessia, entrega, retorno à base) e fica disponível para o próximo despacho.

## 🔘 Funcionalidades

- Seleção de origem e destino por menus dropdown.
- Animação de movimento do AGV ao longo do trilho, com rotação conforme a direção.
- Realce visual (rota "energizada") do trecho de trilho efetivamente utilizado em cada ciclo.
- Indicadores de status do veículo (aguardando / deslocando / coletando / descarregando).
- Painel de KPIs: ciclos concluídos e distância total percorrida.
- Log de eventos com carimbo de hora, para rastrear o histórico da sessão.
- **Três desafios com pontuação**, pensados para conduzir a atividade do workshop:
  1. **Rota direta** (50 pts) — mover carga entre estações no mesmo nível, sem cruzar a linha.
  2. **Rota cruzada** (100 pts) — mover carga entre estações em extremos opostos da planta.
  3. **Cobertura total** (150 pts) — utilizar as três estações de coleta ao longo da sessão.
- Placar de pontuação e notificações de desafio concluído.
- Botão de reinício, para reaproveitar a simulação entre grupos ou turmas.

## 🔘 Como usar

1. Baixe o arquivo `simulador-linha-automatizada.html`.
2. Abra-o em qualquer navegador moderno (Chrome, Firefox, Edge, Safari) — não é necessário servidor ou instalação.
3. Selecione uma estação de origem e uma de destino.
4. Clique em **Despachar AGV** e acompanhe a movimentação.
5. Repita as combinações necessárias para cumprir os três desafios e acumular pontos.
6. Use **Reiniciar simulação** para zerar o cenário entre participantes ou rodadas.

Para uso em workshop, recomenda-se projetar a tela para o grupo ou distribuir o arquivo previamente para que cada participante (ou equipe) rode a simulação em sua própria máquina.

## 🔘 Limitações conhecidas

- Simulação didática: não reflete tempos, distâncias ou lógicas de controle de um AGV real.
- Um único veículo por vez — não há simulação de filas, colisões ou múltiplos AGVs concorrentes.
- Sem persistência entre sessões: útil para dinâmicas de workshop, mas não para acompanhamento de progresso ao longo de várias aulas sem adaptação adicional.

---
