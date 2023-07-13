## 我的 tmux.conf 說明書


## 功能


- Enable mouse mode. (開啟之後好像就能取代 scroll buffer ?)
- Adjust window and pane by mouse. (使用滑鼠調整 pane 大小)
- Keep windows rename (如果不關閉 bash title 自動變更後就會被蓋掉)
- 安裝 tmux-resurrect 儲存當前 tmux session (save: `Prefix + ctrl + s`, restore: `Prefix + ctrl + r`)
- 按下 `Ctrl+Shift+Left` or `Ctrl+Shift+Right` 就能 Swap-windows [ref](https://superuser.com/questions/343572/how-do-i-reorder-tmux-windows)

## tmux reload config


```bash
:source-file ~/.tmux.conf
```

## 安裝 tmux-resurrect plugin 儲存當前 tmux session


[demo video](https://vimeo.com/104763018)

首先要安裝 [Tmux Plugin Manager](https://github.com/tmux-plugins/tpm#tmux-plugin-manager)


```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

在 `~/.tmux.conf` 最底下新增

```conf
# List of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'

# Other examples:
# set -g @plugin 'github_username/plugin_name'
# set -g @plugin 'github_username/plugin_name#branch'
# set -g @plugin 'git@github.com:user/plugin'
# set -g @plugin 'git@bitbucket.com:user/plugin'

# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run '~/.tmux/plugins/tpm/tpm'
```

reload tmux config

```bash
tmux source ~/.tmux.conf
```

接著安裝 tmux-resurrect plugin 本人

[[GitHub] tmux-plugins/tmux-resurrect](https://github.com/tmux-plugins/tmux-resurrect)

在 `~/.tmux.conf` 新增一行

```bash
set -g @plugin 'tmux-plugins/tmux-resurrect'
```

接著 `prefix + I` 開始安裝


## 參考資料


- [[Mouse mode] 終端機管理工具 tmux – Qoding Style](https://blog.qoding.us/2020/12/%E7%B5%82%E7%AB%AF%E6%A9%9F%E7%AE%A1%E7%90%86%E5%B7%A5%E5%85%B7-tmux/)
