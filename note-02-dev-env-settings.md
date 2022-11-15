# Mac 前端開發環境安裝

###### tags: `前端筆記`

- 最後修改日期： 2022-11-14
- 照順序安裝以下工具，準備基本的 HTML / CSS / JS 開發工具

## 目標讀者

- 無任何寫程式的背景或經驗但想嘗試網頁前端開發的人
- [ ] 2022/11/17 星期四，協助醫肝設定環境

## 安裝 CLI 工具

- CLI: Command Line Interface ，也就是「指令列介面」。通常也稱為 Terminal 、終端機等等。通常的使用就是輸入某些指令，按 Enter （或稱 return ），然後電腦做你指示他做的事情。

### 找到 Mac 內建的 terminal 工具

1. command + space 叫出 Spotlight Search 工具

![Spotlight Search](https://i.imgur.com/Oyvt9l0.jpg)

2. 輸入「 terminal 」來搜尋內建的 terminal 軟體

![Mac 內建的 Terminal 軟體](https://i.imgur.com/oK9Lm5G.jpg)

備註： Mac 內建的 Terminal 軟體，如果你的介面預設是中文，他可能顯示的軟體名稱是「終端機」。

3. 打開 Terminal （終端機）軟體，嘗試使用文字指令介面

![Terminal 開啟後的樣子](https://i.imgur.com/ZBD1HjH.jpg)

### 閱讀說明

- 這個說明部分以後的軟體安裝，許多都是照著某個官網的說明，在 Terminal 輸入特定指令來安裝軟體（通常是複製貼上按 Enter ），有空的話建議可以自己稍微閱讀指令的說明文件等等。
- 這份文件主要目的是老翰在與一些朋友一起學習網頁前端開發的參考資料，在其他類似的文件的指令說明可能會是『 $ 』符號或者『 % 』符號開頭，以「 ls 」指令（列出目錄內容）為例：

網路上查詢的教學文件可能會寫：

```
$ ls
```

目前在這個文件上會省略「 $ 」這個提示符號，以方便使用者複製指令，如下：

```
ls
```

以 [brew 官網](https://brew.sh/) 的安裝說明為例，按下複製鍵的時候，並不會複製到「 $ 」的提示符號。

![brew 的官網安裝說明](https://i.imgur.com/H1LGlvG.png)

### 安裝 brew

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

備註：
- [brew官網](https://brew.sh/)
- 「 Homebrew 是一款自由及開放原始碼的軟體套件管理系統，用以簡化 macOS 系統上的軟體安裝過程……」中文維基百科 Homebrew 條目。
- 安裝好 Homebrew 之後，許多軟體或套件都可以用 brew 指令安裝。
- 這類指令可能因時間較久就會改變，有時候還是要到個別軟體或套件的官網確認一下。

### 安裝 VSCode （文字編輯器）

```
brew install --cask visual-studio-code
```

### 安裝 iterm2

```
brew install --cask iterm2
```

備註：
- [brew 的 iterm2 頁面](https://formulae.brew.sh/cask/iterm2)
- [iterm2 官網](https://iterm2.com/)
- 如果安裝後開啟的時候，有詢問要不要給 [iTerm 全磁碟權限 Full Disk Access](https://gitlab.com/gnachman/iterm2/-/wikis/fulldiskaccess) ，要給，比較方便工作。

### 安裝 oh my zsh

```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

- Oh My Zsh 官網文件： [Install oh my zsh](https://ohmyz.sh/#install)

#### Theme: bullet train

洪偉推薦可以用用看的 oh my zsh 主題 bullet train ，好處是可以讓使用者看到現在在使用的 ruby 和 node 版本，適合同時開發一個專案以上的人

- oh-my-zsh 主題： [bullet-train](https://github.com/caiogondim/bullet-train.zsh)
- iterms 的 profile 配色參考使用 [tomorrow](https://github.com/chriskempson/tomorrow-theme)
- 字體： [Meslo LG M Regular for Powerline](https://github.com/powerline/fonts/blob/master/Meslo%20Slashed/Meslo%20LG%20M%20Regular%20for%20Powerline.ttf)
- 安裝參考： https://medium.com/statementdog-engineering/prettify-your-zsh-command-line-prompt-3ca2acc967f

## 安裝或確認 git

查看 git 的版本，有安裝的話會顯示（前面安裝 brew 時應該會一起安裝了）

```
git --version
```

沒有 git 的話可以用 brew 指令安裝

```
brew install git
```

Git 本地端使用者設定（以使用者 jchans 與 email: hanschiang86@gmail.com 為例）

```
git config --global user.name "jchans"
git config --global user.email "hanschiang86@gmail.com"
```

設定完成後可以用以下指令確認目前 git 的使用者設定

```
git config user.name && git config user.email
```


備註：
- [git 官網的 Mac 安裝說明](https://git-scm.com/download/mac)
- Github 的 [ssh key 連線設定](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)


## 安裝 node 與 yarn

安裝 [nvm](https://github.com/nvm-sh/nvm#installing-and-updating)

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.2/install.sh | bash
```

用 nvm 安裝 [nodejs 18](https://nodejs.org/) （Date: 2022-11-08）

```
nvm install 18.12.1
```

安裝 [yarn 2 (3.2.4) ](https://yarnpkg.com/)

Node.js >=18.6

```
corepack enable
corepack prepare yarn@stable --activate
yarn set version stable
```

備註：
- 「Node.js 是能夠在伺服器端運行 JavaScript 的開放原始碼、跨平台執行環境。」，取自[維基百科](https://zh.wikipedia.org/wiki/Node.js)。[ Node.js官網 ](https://nodejs.org/en/)英文簡介：「 Node.js® is an open-source, cross-platform JavaScript runtime environment. 」
- yarn 是 Facebook （現在是 Meta ） 2016 年開發的，用來取代 npm 的套件管理工具，主要目的是處理在較大的專案裡的程式的一致性、安全性與效能等問題。（翻譯自[英文維基百科的 Yarn 條目](https://en.wikipedia.org/wiki/Yarn_(package_manager))）
- yarn 2 有些使用上的細節與 yarn 一版不太一樣，例如[開新的 React 專案] 的指令與一些其他套件或編輯器的設定的方式要注意一些東西，後續的 React 筆記再研究。

```
yarn dlx create-react-app ./my-app
```

## 附錄：老翰個人偏好或筆記

### 用 shell script 完成環境設定

- 老翰重灌電腦，試著把以上設定寫成 [shell script](https://github.com/jchans/new-mac) 

### 安裝 BBEdit （比較輕便的文字編輯器）

```
brew install --cask bbedit
```

### 舊的環境安裝摘要（與上面的安裝說明內容一樣，早期草稿）

一開始寫的環境安裝清單／筆記，存參

安裝 CLI 工具
- Shell 與 Script 說明
- CLI 簡介，簡易 shell 指令教學，[參考](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line)
- [homebrew](https://brew.sh/)
- [iterms2](https://iterm2.com/features.html) 
- [oh my zsh](https://ohmyz.sh/)
- [git](https://git-scm.com/) (先不用教學，設定帳號 email)
- [Guake 模式設定](https://blog.mestwin.net/drop-down-terminal-in-macos-with-iterm2/) （optional）

安裝前端開發工具
- [nvm](https://github.com/nvm-sh/nvm#installing-and-updating)
- [nodejs 18](https://nodejs.org/) （Date: 2022-11-08）
- [yarn 2](https://yarnpkg.com/) 有些安裝的細節與 yarn 一版不太一樣，例如[開新的 React 專案](https://yarnpkg.com/cli/dlx)：
```
yarn dlx create-react-app ./my-app
```

安裝其他開發工具
- [VSCode](https://code.visualstudio.com/)
- VSCode 必要的 extension
    - [Prettier](https://prettier.io/)
    - [Eslint](https://eslint.org/)
    - indent-rainbow
    - Todo Highlight

Optional （非必要，老翰個人偏好）
- 字體： [Cascadia (Code|Mono) PL](https://github.com/microsoft/cascadia-code/releases)
- [BBEdit 文字編輯器](https://apps.apple.com/tw/app/bbedit/id404009241)

參考資料：
- [8 Ways I Use HomeBrew on macOS to Increase Productivity](https://medium.com/@aplaceofmind/i-install-all-macos-apps-using-homebrew-to-increase-productivity-7fc2d511bcc3)

### 協助安裝或教學記錄

- [x] 2022/11/08 星期二，協助小路設定環境
