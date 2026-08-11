#  Máquina de Tickets do Metrô

Simulação embarcada de uma máquina de venda de bilhetes de metrô, desenvolvida em C para o microcontrolador **PIC18F4520**, simulado na placa virtual **PQDB** do **PICSimLab**.

> Projeto Final da disciplina **ECOP14 — Introdução a Sistemas Embarcados** (UNIFEI), Prof. Otávio Gomes — 2021.2.

##  Sobre o projeto

O usuário escolhe, por meio de um teclado matricial, a zona de destino (Norte, Sul, Leste ou Oeste) e a quantidade de bilhetes desejada. O sistema exibe as informações em um display LCD e mostra a quantidade de bilhetes em displays de 7 segmentos. LEDs indicam visualmente a zona selecionada e a confirmação da compra. Ao confirmar, a máquina simula a leitura do "cartão" e exibe o valor total a pagar e a senha digitada para validação da compra.

##  Funcionalidades utilizadas

O projeto atende ao requisito de utilizar pelo menos quatro das funcionalidades propostas, implementando:

| Funcionalidade | Uso no projeto |
|---|---|
| **Display LCD** | Exibe o menu de destino, valor a pagar e campo de senha |
| **Teclado matricial** | Seleciona destino, ajusta quantidade de bilhetes e digita a senha |
| **Displays de 7 segmentos** | Mostram a quantidade de bilhetes selecionada |
| **Barra de LEDs** | Indica a zona de destino escolhida e a confirmação da compra |

##  Tecnologias e ferramentas

- **Microcontrolador:** PIC18F4520
- **Simulador:** [PICSimLab](https://sourceforge.net/projects/picsim/) (placa **PQDB**)
- **IDE:** MPLAB X IDE
- **Compilador:** XC8
- **Linguagem:** C

##  Estrutura do código

| Arquivo | Descrição |
|---|---|
| `main.c` | Lógica principal: máquina de estados do fluxo de venda (seleção de destino → quantidade → confirmação → pagamento) |
| `lcd.c` / `lcd.h` | Controle do display LCD |
| `keypad.c` / `keypad.h` | Leitura do teclado matricial |
| `ssd.c` / `ssd.h` | Controle dos displays de 7 segmentos |
| `timer.c` / `timer.h` | Base de tempo usada no loop principal |
| `atraso.c` / `atraso.h` | Rotinas de atraso (delay) em milissegundos |
| `io.c` / `io.h` | Funções auxiliares de entrada/saída digital (`digitalWrite`, `digitalRead`, `pinMode`) |
| `bits.h` | Macros para manipulação de bits |
| `config.h` | Configurações (fuses) do microcontrolador |
| `ds1307.c` / `ds1307.h`, `i2c.c` / `i2c.h` | Bibliotecas de RTC/I2C disponibilizadas para o projeto (não utilizadas na versão atual) |

##  Como executar

1. Instale o [MPLAB X IDE](https://www.microchip.com/en-us/development-tools-tools-and-software/mplab-ecosystem-downloads-archive) e o compilador **XC8**.
2. Instale o [PICSimLab](https://sourceforge.net/projects/picsim/) (versão 0.8.8 ou superior) e selecione a placa **PQDB** com o microcontrolador **PIC18F4520**.
3. Clone este repositório e abra o projeto no MPLAB X IDE.
4. Compile o projeto (gera o arquivo `.hex`).
5. Carregue o `.hex` gerado no PICSimLab e inicie a simulação.
6. Use o teclado virtual para escolher o destino, ajustar a quantidade de bilhetes e confirmar a compra.

##  Créditos

As bibliotecas base de `lcd`, `ssd`, `keypad`, `timer`, `config` e `bits` foram fornecidas pelo professor Rodrigo Maximiano Antunes de Almeida (UNIFEI) para uso na disciplina, sob licença GNU GPL v2.
