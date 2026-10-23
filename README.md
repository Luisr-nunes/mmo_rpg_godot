# MMO RPG — Cliente Godot

<!-- badges -->
![GDScript](https://img.shields.io/badge/GDScript-478CBF?style=flat-square&logo=godotengine&logoColor=white) ![Godot 4](https://img.shields.io/badge/Godot%204-478CBF?style=flat-square&logo=godotengine&logoColor=white) ![WebSocket](https://img.shields.io/badge/WebSocket-010101?style=flat-square&logo=socketdotio&logoColor=white)

[Read in English](README.en.md)

Cliente em Godot 4 para o protótipo [MMO RPG](https://github.com/Luisr-nunes/mmo_rpg), usado para comparar a engine com o cliente Unity sobre o mesmo servidor.

## Sobre

O cliente conecta ao servidor WebSocket do projeto `mmo_rpg`, envia movimento e ações de coleta e desenha o mundo a partir do estado recebido. Toda a lógica do jogo (posições, recursos, rolagens de d20, inventário) fica no servidor; o cliente apenas exibe e envia comandos.

## Funcionalidades

- Conexão a `ws://localhost:8765` com indicação de estado (conectando, conectado, desconectado).
- Movimento com WASD ou setas.
- Coleta do recurso mais próximo com Espaço ou Enter.
- Exibição do resultado das rolagens de d20 e da quantidade de madeira no inventário.
- Renderização de fundo, jogadores e árvores com sprites próprios em `assets/`.

## Tecnologias

- Godot 4 (renderizador Forward+)
- GDScript com `WebSocketPeer`
- Mensagens JSON: `init`, `game_state`, `dice_roll` (servidor) e `move`, `collect` (cliente)

## Estrutura

```
mmo_rpg_godot/
├── project.godot   # configuração do projeto
├── Main.tscn       # cena principal
├── Main.gd         # rede, entrada do jogador e desenho
└── assets/         # bg.png, player.png, objects.png
```

## Como executar

1. Inicie o servidor do projeto principal:

   ```bash
   git clone https://github.com/Luisr-nunes/mmo_rpg.git
   cd mmo_rpg
   pip install websockets
   python server/server.py
   ```

2. Abra este projeto no Godot 4 (Import → `project.godot`) e pressione F5. A cena `Main.tscn` é carregada automaticamente.

## Autor

Luís Nunes — [GitHub](https://github.com/Luisr-nunes) · [LinkedIn](https://www.linkedin.com/in/luis-nunes-dev/)
