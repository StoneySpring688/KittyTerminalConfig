# KittyTerminalConfig
Mi Configuración de la terminal Kitty y zsh.

## Dependencias

>[!IMPORTANT]
> Es aconsejable instalar las dependencias en este orden

>[!TIP]
> p10k y starship sirven para configurar el prompt de la terminal\
> Se puede omitir de uno de los dos si se desea\
> Si se prescinde de p10k es aconsejable cambiar ```ZSH_THEME="powerlevel10k/powerlevel10k"``` a esto ```ZSH_THEME="agnoster"``` en ```.zshrc```, así como eliminar el fichero ```.p10k.zsh```\
> Si se prescinde de starship comentar ```eval "$(starship init zsh)"``` al final de ```.zshrc```, así como eliminar el fichero ```.config/starship.toml```

### 1. NerdFonts

Pueden instalarse las que se quiera desde [aquí](https://www.nerdfonts.com/font-downloads), siempre que se configuren correctamente en ```.zshrc```.
  
Por defecto se ofrecen unas [NerdFonts](Hack) llamadas Hack las cuales ya están configuradas en esta instalación.

Para instalarlas selecciona ```HackNerdFont-Regular.ttf``` en el directorio ```Hack```, abrela con la aplicación de tipografías y haz click en instalar.


### 2.Kitty
```bash
sudo apt install kitty
```


### 3. zsh
```bash
sudo apt install zsh
```


### 4. oh my zsh
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```


### 5. starship
```bash
curl -sS https://starship.rs/install.sh | sh
```


### 6. powelevel10k
```bash
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```


### 7. fastfetch
  
En el caso de Ubuntu se pueden usar los siguientes comandos:
```bash
sudo add-apt-repository ppa:zhangsongcui3371/fastfetch
sudo apt update
sudo apt install fastfetch
```
En el caso de Arch, se puede instalar con pacman:
```bash
sudo pacman -S fastfetch
```

### 8. tmux

```bash
sudo apt install tmux
```


## Configuración
### 1. Clonar el repositorio y copiar los contenidos

Clonar el repositorio y entrar al directorio
```bash
git clone https://github.com/StoneySpring688/KittyTerminalConfig.git
cd KittyTerminalConfig/
```
Para copiar los contenidos del repositorio a su destino
```bash
rsync -av --exclude='.git' --exclude='README.md' --exclude='Hack/' ./ ~/
cd
```


### 2. Establecer zsh como interprete de ordenes predeterminado
```bash
chsh -s $(which zsh)
```
Si usas otra terminal también tomará zsh como Shell, si quieres que esa terminal use bash o fish deberás configurarlo
    
Para la terminal de gnome :
   1.  Preferencias
   2.  Elige un perfil o haz uno nuevo
   3.  Comando
   4.  Activa ```Ejecutar una orden personalizada en vez de mi intérprete```
   5.  En orden peronalizada pon ```bash```
   6.  Cambia ```Cuando la orden termina``` a ```Mantener el terminal abierto```


### 3. Instalar plugins de oh-my-zsh
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```
El primer plugin muestra un "hint" que facilita completar el comando y el segundo plugin resalta la sintaxis del mismo.

Normalmente habría que incluir los plugins en ```zshrc``` pero en este caso ya está todo configurado


### 4. Elegir entre p10k o starship

Si la eleccion es p10k bastará con comentar la última línea al fina de ```.zshrc``` la cual es ```eval "$(starship init zsh)"```.
   
Si por el contrario se quiere usar starship, bastará con cambiar ```ZSH_THEME="powerlevel10k/powerlevel10k"``` a esto ```ZSH_THEME="agnoster"``` en ```.zshrc```.


### 5. Shortcuts

Al introducir el comando
```zsh
kittyhelp
```
en la terminal de kitty, se mostrará una pequeña guía con los shortcuts.

Para los shortcuts de mover y redimensionar la ventana es necesario configurarlos en el entorno de GNOME, KDE, o el que se esté usando.

En el caso de GNOME solo hay que configurar el shortcut para redimensionar la ventana, con este comando:
```bash
gsettings set org.gnome.desktop.wm.keybindings begin-resize "['<Super><Shift>r']"
```
Con este otro comprueba que se haya configurado correctamente:
```bash
gsettings get org.gnome.desktop.wm.keybindings begin-resize
```
Debería devolver esto : ```['<Super><Shift>r']```
  
### 6. instalar plugins de tmux

Para instalar los plugins definidos en ```.tmux.conf``` hay que instalar el *tpm*
```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```
Tras eso, inicia tmux usando el shortcut```ctrl + t``` y haz ```ctrl + a , shift + i``` para instalar los plugins.\
Después haz ```ctrl + a , r``` para recargar la configuración de tmux.
