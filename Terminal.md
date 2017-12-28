# Terminal

### Encurtar o caminho do diretório
Deixe visível, no caminho de pastas, somente o diretório atual

Para efeito temporário no terminal aberto, no mesmo execulte o comando `PS1='\u:\W\$ '`

Se a sua ideia é que fique permanente então...  
Abra o arquivo .bashrc localizado em /home/usuario/ e localize a instrução
```
if [ "$color_prompt" = yes ]; then
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
else
    PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
fi
```
remova o `@\h`, e substitua o `\w` por `\W` com maiúscula, de modo que se torne:
```
if [ "$color_prompt" = yes ]; then
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u\[\033[00m\]:\[\033[01;34m\]\W\[\033[00m\]\$ '
else
    PS1='${debian_chroot:+($debian_chroot)}\u:\W\$ '
fi
```
