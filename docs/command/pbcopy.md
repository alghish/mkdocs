# Pbcopy & Pbpaste

Pbcopy And Pbpaste Commands On Linux

## Installation

On Debian, Ubuntu, Linux Mint:

```bash
  sudo apt install xclip xsel
```

## Steps Install

### 1- Installed, you need create aliases for pbcopy and pbpaste commands. To do so, edit your ~/.bashrc file:

```bash
  vim ~/.bashrc
```

### 2- Add alias

```bash
 alias pbcopy='xclip -selection clipboard'
 alias pbpaste='xclip -selection clipboard -o'
```

### 3- update the changes in ~/.bashrc file.

```bash
  source ~/.bashrc
```

## Tested

```bash
  echo "Welcome To OSTechNix!" | pbcopy
  echo `pbpaste`
```

## References

- [How To Use Pbcopy And Pbpaste Commands On Linux](https://ostechnix.com/how-to-use-pbcopy-and-pbpaste-commands-on-linux/)
