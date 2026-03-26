# Como configurar/instalar/usar o `desabilitar o touchpad/mousepad` no `Linux Ubuntu`

## Resumo

Neste documento estão contidos os principais comandos e configurações para configurar/instalar/usar o `desabilitar o touchpad/mousepad` no `Linux Ubuntu`.

## _Abstract_

_In this document are contained the main commands and settings to set up/install/use the `desabilitar o touchpad/mousepad` on `Linux Ubuntu`._


## Descrição [2]

### `touchpad/mousepad`

O `touchpad`, também conhecido como `mousepad`, é um dispositivo de entrada comum em _laptops_ e _notebooks_, usado para controlar o cursor na tela. Ele funciona detectando o movimento dos dedos sobre sua superfície sensível ao toque. Além de mover o cursor, o `touchpad` pode ser usado para clicar, arrastar e executar outras funções, dependendo das configurações do sistema operacional. Geralmente localizado abaixo do teclado, o `touchpad` oferece uma maneira conveniente e intuitiva de interagir com o computador, especialmente em ambientes onde o uso de um _mouse_ tradicional não é prático.


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

    2.4 Buscar as atualizações disponíveis para os pacotes que estão instalados em seu sistema. Digite o seguinte comando e pressione `Enter`:
    ```bash
    sudo apt update
    ```

    2.5 **Corrigir pacotes quebrados**: Isso atualizará a lista de pacotes disponíveis e tentará corrigir pacotes quebrados ou com dependências ausentes:
    ```bash
    sudo apt --fix-broken install
    ```

    2.6 Limpar o `cache` do gerenciador de pacotes `apt` novamente:
    ```bash
    sudo apt clean
    ```

    2.7 Para ver a lista de pacotes a serem atualizados, digite o seguinte comando e pressione `Enter`:
    ```bash
    sudo apt list --upgradable
    ```

    2.8 Realmente atualizar os pacotes instalados para as suas versões mais recentes, com base na última vez que você executou `sudo apt update`. Digite o seguinte comando e pressione `Enter`:
    ```bash
    sudo apt full-upgrade -y
    ```

Para desabilitar o `touchpad` (ou `mousepad`) no `Linux Ubuntu`, você pode utilizar várias abordagens, dependendo de suas preferências e da versão do `Linux Ubuntu` que está usando. Vou te mostrar dois métodos comuns: um usando a interface gráfica e outro pelo `Terminal Emulator`.

### 1.1 Usando a interface gráfica

Para desabilitar o `touchpad` (ou `mousepad`) usando a _interface_ gráfica, siga o passo a passo abaixo:

1. **Configurações do Sistema:** Vá até as configurações do sistema clicando no ícone do sistema ou procurando por `"Settings Manager"` no menu de aplicações.

2. **Dispositivos / Mouse e Touchpad:** Procure pela seção `"Hardware"`, `"Mouse and Touchpad`" ou similar, dependendo da versão do `Linux Ubuntu`.

3. **Desativar Touchpad:** Você deve encontrar uma opção para desabilitar o `touchpad`. Esta opção pode ser um interruptor ou caixa de seleção que diz `"Disable touchpad"` ou `"Disable touchpad while typing"`.


### 1.2 Usando o `Terminal Emulator`

Para uma abordagem mais direta e que funciona independentemente da _interface_ gráfica que você está usando, você pode desabilitar o `touchpad` através do `Terminal Emulator`.

1. Abrir o `Terminal Emulator`. Você pode fazer isso pressionando:

    ```bash
    Ctrl + Alt + T
    ```    

2. **Identificar o Dispositivo**: Primeiro, você precisa identificar o seu `touchpad`:

    ```bash
    xinput list
    ```

    Você vai ver algo como:

    ```bash
    xinput list ⎡ Virtual core pointer id=2 [master pointer (3)]
    ↳ Virtual core XTEST pointer id=4 [slave pointer (2)]
    ⎜ ↳ DLL07B0:01 044E:120B id=11 [slave pointer (2)]
    ⎜ ↳ DualPoint Stick id=12 [slave pointer (2)]
    ⎜ ↳ PS/2 Generic Mouse id=17 [slave pointer (2)]
    ⎜ ↳ Logitech M720 Triathlon Multi-Device Mouse id=18 [slave pointer (2)]
    ⎣ Virtual core keyboard id=3 [master keyboard (2)]
      ↳ Virtual core XTEST keyboard id=5 [slave keyboard (3)]
      ↳ Power Button id=6 [slave keyboard (3)]
      ↳ Video Bus id=7 [slave keyboard (3)]
      ↳ Video Bus id=8 [slave keyboard (3)]
      ↳ Power Button id=9 [slave keyboard (3)]
      ↳ Sleep Button id=10 [slave keyboard (3)]
      ↳ Intel HID 5 button array id=13 [slave keyboard (3)]
      ↳ Intel HID events id=14 [slave keyboard (3)]
      ↳ Dell WMI hotkeys id=15 [slave keyboard (3)]
      ↳ AT Translated Set 2 keyboard id=16 [slave keyboard (3)]
      ↳ Logitech M720 Triathlon Multi-Device Mouse id=19 [slave keyboard (3)]
    ```

    Para o notebook Dell Precision 7520, o `touchpad` é esse:

    ```bash
    DLL07B0:01 044E:120B   id=11
    ```

3. **Encontrar o `touchpad`**: Procure na lista um dispositivo que parece ser o seu `touchpad`. Geralmente é identificado como `Touchpad` ou algo similar.

4. **Desabilitar o `touchpad`**: Depois de identificar o nome ou `ID` do seu `touchpad`, use o seguinte comando para desabilitá-lo, substituindo `ID` pelo número do `ID` do seu `touchpad`:

    ```bash
    xinput --disable ID
    ```

    Por exemplo, se o `ID` do seu `touchpad` for `11`, o comando será:
    
    ```bash
    xinput --disable 11
    ```

**Nota:** Para reativar o `touchpad`, você pode usar o comando:

    ```bash
    xinput --enable ID
    ```
    
    Substitua o `ID` pelo número do `ID` do seu `touchpad`.

Esses métodos devem ajudar você a evitar acidentalmente tocar no `touchpad` enquanto usa um mouse externo.


### 1.2 Código completo para configurar/instalar

Para configurar/instalar/usar o `desabilitar o touchpad/mousepad` no `Linux Ubuntu` sem precisar digitar linha por linha, você pode seguir estas etapas:

1. Abrir o `Terminal Emulator`. Você pode fazer isso pressionando:

    ```bash
    Ctrl + Alt + T
    ```

2. Digite o seguinte comando e pressione `Enter`:

    ```bash
    **NÃO há.**
    ```
    

## 2. _Aliases_

1. Abrir o `Terminal Emulator`. Você pode fazer isso pressionando:

    ```bash
    Ctrl + Alt + T
    ```

2. Digite o seguinte comando para abrir o arquivo de configuração do shell:


    - **Bash**:
    
    ```bash
    sudo nano ~/.bashrc
    ```

    - **Zsh**:

    ```bash
    sudo nano ~/.zshrc
    ```

3. Adicione as seguintes linhas ao final do arquivo para criar aliases úteis:

    ```bash
    # --- Desativar/Ativar o touchpad/mousepad ---
    alias touchpad_off='xinput disable "DLL07B0:01 044E:120B"'
    alias touchpad_on='xinput enable "DLL07B0:01 044E:120B"'
    ```

    **NÃO** esqueça de trocar o `ID` que está como `DLL07B0:01 044E:120B` pelo `ID` do seu dispositivo. 

## Referências

[1] OPENAI. **Instalar o `desabilitar o touchpad/mousepad` no `linux ubuntu` pelo `terminal emulator`.*** Disponível em: <https://chatgpt.com/c/69c47376-e424-83e9-a3a8-bb5d07073e02> (texto adaptado). ChatGPT. Acessado em: 25/02/2024 12:00.

[2] OPENAI. **Vs code: editor popular.** Disponível em: <https://chat.openai.com/c/b640a25d-f8e3-4922-8a3b-ed74a2657e42> (texto adaptado). ChatGPT. Acessado em: 25/02/2024 12:00.

