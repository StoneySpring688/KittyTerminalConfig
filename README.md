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
  sudo apt install kitty
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
