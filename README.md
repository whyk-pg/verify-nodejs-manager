# Verify Node.js Manager

## 本リポジトリの目的
以下の要件に見合うNode.jsのバージョン管理ツールを探す。

- マルチプラットフォーム(Windows, macOS, Linux)対応
  - マルチプラットフォーム対応でなければWSLを使う方針にする
- バージョンの自動切替
- pnpmなどはCorepackで管理
- Cloudflare Pagesの`NODE_VERSION`を実装側と同期
- GitHub Actions上のNode.js環境セットアップを`actions/setup-node`のみにする
- 手動での二重管理をなくす

### 調査対象
- [fnm](https://github.com/Schniz/fnm)
- [nodenv](https://github.com/nodenv/nodenv)
- [nvm](https://github.com/nvm-sh/nvm)
- [n](https://github.com/tj/n)

### 調査方法
proto以外で一通りの環境構築を行なう。
最初にVoltaで環境構築を行ない、上から順にセットアップを行なう。
Windows非対応でもWSLでは動くので、もしWindows対応で使えるものがなければ調査する。

### 星取表
| Software name | multi platform support | Node.js version auto switch | Corepack can enable | `.node-version` or `.nvmrc` support |
| ------------- | ---------------------- | --------------------------- | ------------------- | ----------------------------------- |
| Volta         | Yes                    | Yes                         | Yes                 | No                                  |
| proto         | Yes                    | Yes                         | No                  | Yes                                 |
| fnm           | Yes                    | ?                           | ?                   | ?                                   |
| nodenv        | No                     | ?                           | ?                   | ?                                   |
| nvm           | No                     | ?                           | ?                   | ?                                   |
| n             | No                     | ?                           | ?                   | ?                                   |

## 本リポジトリの達成目標
- [x] Voltaで初期環境構築を行なう
- [x] Cloudflare Pagesにアップロード
- [x] fnmで環境再構築を行なう
- [ ] Voltaでの環境構築を前提に、CIで.node-versionと現行バージョンの確認を行なう

## 参考資料
- 特になし
