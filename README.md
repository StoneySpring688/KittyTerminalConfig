# KittyTerminalConfig
Mi Configuración de la terminal Kitty y zsh.

>[!IMPORTANT]
>Es necesario instalar las dependencias

### Dependencias
- NerdFonts

  Pueden instalarse las que se quiera desde [aquí](https://www.nerdfonts.com/font-downloads), siempre que se configuren correctamente en ```.zshrc```.
  
  Por defecto se ofrecen unas [NerdFonts](Hack) llamadas Hack las cuales ya están configuradas en esta instalación.

  Para instalarlas selecciona ```HackNerdFont-Regular.ttf``` en el directorio ```Hack```, abrela con la aplicación de tipografías y haz click en instalar.

- Kitty
  ```bash
  sudo apt install kitty
  ```
- zsh
  ```bash
  sudo apt install zsh
  ```
- oh my zsh
  ```bash
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  ```
- starship
  ```bash
  curl -sS https://starship.rs/install.sh | sh
  ```
- powelevel10k
  ```bash
  git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
  ```

### Configure
1. Clonar el repositorio y copiar los contenidos

    Clonar el repositorio y entrar al directorio
     ```bash
     git clone https://github.com/StoneySpring688/KittyTerminalConfig.git
     cd KittyTerminalConfig/
     ```
    Para copiar los contenidos del repositorio a su destino
    ```bash
    cp -r $(find . -mindepth 1 -not -path './.git*' -not -name 'README.md') ~/
    cd
    ```
3. Establecer zsh como interprete de ordenes predeterminado
    ```bash
    chsh -s $(which zsh)
    ```
4. Instalar plugins de oh-my-zsh
   ```bash
   git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
   git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
   ```
   El primer plugin muestra un "hint" que facilita completar el comando y el segundo plugin resalta la sintaxis del mismo.

   Normalmente habría que incluir los plugins en ```zshrc``` pero en este caso ya está todo configurado
5. Elegir entre p10k o starship

   Si la eleccion es p10k bastará con comentar la última línea al fina de ```.zshrc``` la cual es ```eval "$(starship init zsh)"```.
   
   Si por el contrario se quiere usar starship, no será necesario realizar ninguna configuración adicional.
