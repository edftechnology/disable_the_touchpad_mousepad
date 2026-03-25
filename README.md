# Como configurar/instalar/usar o `desabilitar o touchpad/mousepad` no `Linux Ubuntu`

## Resumo

Neste documento estão contidos os principais comandos e configurações para configurar/instalar/usar o `desabilitar o touchpad/mousepad` no `Linux Ubuntu`.

## _Abstract_

_In this document are contained the main commands and settings to set up/install/use the `desabilitar o touchpad/mousepad` on `Linux Ubuntu`._


## Descrição [2]

### `touchpad/mousepad`

O touchpad, também conhecido como mousepad, é um dispositivo de entrada comum em laptops e notebooks, usado para controlar o cursor na tela. Ele funciona detectando o movimento dos dedos sobre sua superfície sensível ao toque. Além de mover o cursor, o touchpad pode ser usado para clicar, arrastar e executar outras funções, dependendo das configurações do sistema operacional. Geralmente localizado abaixo do teclado, o touchpad oferece uma maneira conveniente e intuitiva de interagir com o computador, especialmente em ambientes onde o uso de um mouse tradicional não é prático.


## 1. Como configurar/instalar/usar o `desabilitar o touchpad/mousepad` no `Linux Ubuntu` [1][3]

Para configurar/instalar/usar o `desabilitar o touchpad/mousepad` no `Linux Ubuntu`, você pode seguir estes passos:

1. Abrir o `Terminal Emulator`. Você pode fazer isso pressionando:

    ```bash
    Ctrl + Alt + T
    ```    

2. Certifique-se de que seu sistema esteja limpo e atualizado.

    2.1 Limpar o `cache` do gerenciador de pacotes `apt`. Especificamente, ele remove todos os arquivos de pacotes (`.deb`) baixados pelo `apt` e armazenados em `/var/cache/apt/archives/`. Digite o seguinte comando:
    ```bash
    sudo apt clean
    ```
    
    2.2 Remover pacotes `.deb` antigos ou duplicados do `cache` local. É útil para liberar espaço, pois remove apenas os pacotes que não podem mais ser baixados (ou seja, versões antigas de pacotes que foram atualizados). Digite o seguinte comando:
    ```bash
    sudo apt autoclean
    ```

    2.3 Remover pacotes que foram automaticamente instalados para satisfazer as dependências de outros pacotes e que não são mais necessários. Digite o seguinte comando:
    ```bash
    sudo apt autoremove -y
    ```

    2.4 Buscar as atualizações disponíveis para os pacotes que estão instalados em seu sistema. Digite o seguinte comando e pressione `Enter`: `sudo apt update -y`

    2.5 Para ver a lista de pacotes a serem atualizados, digite o seguinte comando e pressione `Enter`:  `sudo apt list --upgradable`

    2.6 Realmente atualizar os pacotes instalados para as suas versões mais recentes, com base na última vez que você executou `sudo apt update -y`. Digite o seguinte comando e pressione `Enter`: `sudo apt full-upgrade -y`

    2.7 Remover pacotes que foram automaticamente instalados para satisfazer as dependências de outros pacotes e que não são mais necessários. Digite o seguinte comando: `sudo apt autoremove -y`

    2.8 Remover pacotes `.deb` antigos ou duplicados do cache local. É útil para liberar espaço, pois remove apenas os pacotes que não podem mais ser baixados (ou seja, versões antigas de pacotes que foram atualizados). Digite o seguinte comando: `sudo apt autoclean`

Para desabilitar o `touchpad` (ou `mouse pad`) no `Linux Ubuntu`, você pode utilizar várias abordagens, dependendo de suas preferências e da versão do `Ubuntu` que está usando. Vou te mostrar dois métodos comuns: um usando a interface gráfica e outro pelo terminal.

### 1.1 Usando a interface gráfica

Para desabiliyat o `touchpad` (ou `mouse pad`) usando a interface gráfica, siga o passo a passo abaixo:

1. **Configurações do Sistema:** Vá até as configurações do sistema clicando no ícone do sistema ou procurando por `"Settings Manager"` no menu de aplicações.

2. **Dispositivos / Mouse e Touchpad:** Procure pela seção `"Hardware"`, `"Mouse and Touchpad`" ou similar, dependendo da versão do `Ubuntu`.

3. **Desativar Touchpad:** Você deve encontrar uma opção para desabilitar o `touchpad`. Esta opção pode ser um interruptor ou caixa de seleção que diz `"Disable touchpad"` ou `"Disable touchpad while typing"`.


### 1.2 Usando o `Terminal Emulator`

Para uma abordagem mais direta e que funciona independentemente da interface gráfica que você está usando, você pode desabilitar o touchpad através do terminal.

1. **Identificar o Dispositivo:** Primeiro, você precisa identificar o seu touchpad. Abra o terminal e digite: `xinput list`

2. **Encontrar o Touchpad:** Procure na lista um dispositivo que parece ser o seu touchpad. Geralmente é identificado como "Touchpad" ou algo similar.

3. **Desabilitar o Touchpad:** Depois de identificar o nome ou ID do seu touchpad, use o seguinte comando para desabilitá-lo, substituindo ID pelo número do ID do seu touchpad: `xinput --disable ID`

    Por exemplo, se o ID do seu touchpad for `12`, o comando será: `xinput --disable 12`

**Nota:** Para reativar o touchpad, você pode usar o comando `xinput --enable ID`, substituindo ID pelo número do ID do seu touchpad.

Esses métodos devem ajudar você a evitar acidentalmente tocar no touchpad enquanto usa um mouse externo.


### 1.2 Código completo para configurar/instalar

Para configurar/instalar/usar o `desabilitar o touchpad/mousepad` no `Linux Ubuntu` sem precisar digitar linha por linha, você pode seguir estas etapas:

1. Abrir o `Terminal Emulator`. Você pode fazer isso pressionando:

    ```bash
    Ctrl + Alt + T
    ```

2. Digite o seguinte comando e pressione `Enter`:

    ```
    **NÃO há.**
    ```
    

## Referências

[1] OPENAI. ***desabilitar o touchpad/mousepad.*** Disponível em: <https://chat.openai.com/c/b640a25d-f8e3-4922-8a3b-ed74a2657e42> (texto adaptado). ChatGPT. Acessado em: 25/02/2024 12:00.

[2] OPENAI. ***Vs code: editor popular.*** Disponível em: <https://chat.openai.com/c/b640a25d-f8e3-4922-8a3b-ed74a2657e42> (texto adaptado). ChatGPT. Acessado em: 25/02/2024 12:00.

