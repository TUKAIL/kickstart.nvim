# Tmux Cheatsheet

## Key Commands

Start a new session

```shell
tmux new -s NewSession
```

Exit session

```shell
tmux detach
```

List sessions

```shell
tmux ls
```

Go back into session

```shell
tmux attach -t NewSession
```

Show all available options

```shell
tmux show-options -g
```

Show all available shortcuts

```shell
tmux list-keys
```

Show all available commands

```shell
tmux list-commands
```

Start fresh

```shell
tmux kill-server && rm -rf /tmp/tmux-*
```

Enable plugins

```shell
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

## Essential Shortcuts

- Prefix: `CTRL + <Space>`
- Create new tmux window: `Prefix + c`
- Navigate to window: `Prefix + number`
- Cycle through window: `Prefix + n/p`
- See all windows: `Prefix + w`
- Rename window: `Prefix + ,`
- Rename session: `Prefix + $`
- Explore sessions: `Prefix + s`
- Save sessions: `Prefix + CTRL + s`
- Detach: `Prefix + d`
- Restore session: `Prefix + CTRL + r`
- Install plugins: `Prefix + I`

快捷键关闭当前窗口：Ctrl + b 然后 &



| 功能                      | 快捷键        |
| ------------------------- | ------------- |
| 分屏                      | Ctrl+b % / "  |
| 切 pane                   | Ctrl+b 方向键 |
| 关闭 pane                 | Ctrl+b x      |
| 放大 pane(临时关掉另一个) | Ctrl+b z      |

Ctrl+b [ 翻到上面去

resize-pane -L 10

pane往左一点：Ctrl-b Alt-→

**tmux 里左右两个 pane 互换位置**：

```
Ctrl-b Ctrl-o
```

也就是先按 `Ctrl-b`，再按 `Ctrl-o`，会把 pane 顺时针交换。

## Useful Snippets

Add this to you `.zshrc` to always work in a Tmux session:

```shell
# Always work in a tmux session if Tmux is installed
if which tmux 2>&1 >/dev/null; then
  if [ $TERM != "screen-256color" ] && [  $TERM != "screen" ]; then
    tmux attach -t default || tmux new -s default; exit
  fi
fi
```
