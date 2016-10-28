# Super zsh Kit Basic

## How to Use

Let's use [`zim`](https://github.com/Eriner/zim) instead of `prezto` or `oh-my-zsh` to tune up our zsh shell! Why? It's blazing fast!

1. Clone the zim.

```sh
git clone --recursive https://github.com/Eriner/zim.git ${ZDOTDIR:-${HOME}}/.zim
```

2. Set our shell to zsh.

```sh
chsh -s /bin/zsh
```

3. Initialize the configs.

```sh
setopt EXTENDED_GLOB
for template_file ( ${ZDOTDIR:-${HOME}}/.zim/templates/* ); do
  user_file="${ZDOTDIR:-${HOME}}/.${template_file:t}"
  touch ${user_file}
  ( print -rn "$(<${template_file})$(<${user_file})" >! ${user_file} ) 2>/dev/null
done
```

4. Finish optimization.

```sh
source ${ZDOTDIR:-${HOME}}/.zlogin
```

5. Then examine your `.zshrc` file. That's it!
