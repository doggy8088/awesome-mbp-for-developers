# MacBook Pro（MBP）必裝軟體與實用設定精華整理

本文整理自 [Will 保哥的技術交流中心](https://www.facebook.com/will.fans) LINE 社群的討論串，內容涵蓋「新入手 MacBook Pro 後，最常被推薦安裝的軟體、終端機選擇、視窗管理、快捷鍵、輸入法、觸控板與工作流工具」，適合 **Windows 轉 Mac** 與 **進階使用者** 快速建立順手環境。

---

## 一、套件管理與基礎工具

### Homebrew（必裝）
macOS 最主流的套件管理工具，可同時管理 CLI 與桌面應用（cask）。

- 官方網站：https://brew.sh/
- 可安裝：
  - CLI：`git`、`ffmpeg`、`yt-dlp`、`node`…
  - GUI：Raycast、iTerm2、Rectangle、Alacritty…

---

### WailBrew（GUI 版本的 Homebrew 管理工具）
圖形化介面的 Homebrew 套件管理工具，讓套件升級與管理更直觀。

- 官方專案：https://github.com/wickenico/WailBrew
- 核心功能：
  - 視覺化列出所有可升級的套件
  - 一鍵批次更新與管理
  - 支援多國語言（i18n），降低語言門檻
  - 友善的圖形介面，無需記憶指令

雖然 `brew install` 與 `brew upgrade` 相當方便，但對於「想快速確認有哪些套件可以升級」的使用者來說，WailBrew 提供了更直覺的操作體驗。

---

### Oh My Zsh（必裝）
Zsh 設定與外掛管理框架，用來快速建立可維護、可擴充的終端機環境。  
在工程師社群中屬於「裝了才開始用 Mac 終端機」的基本配備。

- 官方網站：https://ohmyz.sh/
- 核心價值：
  - 統一管理 `.zshrc` 與 shell 設定
  - 內建大量常用 plugin（`git`、`docker`、`kubectl` 等）
  - 主題與外掛即插即用，降低設定門檻

#### 補充：Zimfw 也值得試
- 有些使用者會選擇 **Zimfw** 來管理 Zsh plugin，常見回饋是效能表現不錯
- 實務上也有使用者反映：終端機啟動速度會比 Oh My Zsh 再快一點點
- 建議兩者都試用，再依你的工作流與啟動速度體感做選擇

#### 推薦外掛
- **Powerlevel10k**（高資訊密度 Prompt）  
  https://github.com/romkatv/powerlevel10k
- **zsh-autosuggestions**：歷史指令自動建議
- **zsh-syntax-highlighting**：指令語法即時上色

#### 實務建議
- 將 Oh My Zsh 與相關設定一併納入 `.dotfiles` 管理
- 與 Homebrew、iTerm2 / Alacritty 搭配，可快速重建完整開發環境

---

## 二、終端機（Terminal）選擇

### iTerm2
最普及的第三方終端機，功能完整、社群資源多。

- https://iterm2.com/
- 優點：
  - 高度可客製化（背景、字型、快捷鍵）
  - 生態成熟，教學資源多

### Alacritty
效能導向、設定檔驅動的終端機，速度極快。

- 官方專案：https://github.com/alacritty/alacritty
- Homebrew：https://formulae.brew.sh/cask/alacritty

#### 特色
- 設定以 YAML/純文字檔為主
- 啟動與渲染速度快、資源消耗低
- 適合追求「原生渲染效能」的工程師

#### macOS Self-Signing（自簽署）說明
因 macOS 對第三方終端機的簽章要求，Alacritty 官方提供自簽署指南：

- 官方文件（GitHub Wiki）：  
  https://github.com/alacritty/alacritty/wiki/Self-Signing-Alacritty-on-macOS

內容包含：
- 建立自簽章憑證（Keychain）
- 簽署 Alacritty 執行檔
- Gatekeeper / Debug 設定流程

> Self-Signing 為不使用 Apple Developer 帳號的替代方案，適合可自行維護工具鏈的使用者。

#### Homebrew 上的 Status
- Homebrew cask 目前顯示 **deprecated**
- 原因與 macOS 簽章政策與發行責任歸屬有關
- 不代表無法使用，而是提醒安裝與簽署流程需自行處理

### 其他選項（依需求）
- **Ghostty**：新興終端機，討論熱度上升
- **Warp**：內建 AI 輔助，但耗電量偏高，定位偏新手

---

## 三、啟動器與工作流工具

### Raycast
高效能啟動器，取代 Spotlight / Alfred。

- 官網：https://www.raycast.com/
- 免費版功能已相當完整
- 延伸閱讀：https://wylin.tw/pages/how-i-use-raycast/
- 常見用途：
  - 快速啟動 App
  - 執行 Script / Workflow
  - 剪貼簿、視窗、指令整合

---

## 四、鍵盤、快捷鍵與輸入法

### Karabiner-Elements（鍵位重映射）
讓非 Mac 鍵盤、Windows 使用者快速適應 macOS。

- https://karabiner-elements.pqrs.org/
- 用途：
  - 調整 Command / Control / Option
  - 中英文切換行為調整
- 參考教學：https://blog.lusyoe.com/article/mac-key-remap-karabiner-elements

### 中英文輸入法建議
- **自然輸入法（第三方）**  
  https://share.google/crWjc2wshOKKBOuOE  
  支援 Shift 切換中英文，操作邏輯接近 Windows
- **唯音輸入法**  
  適合不習慣原生輸入法者

---

## 五、視窗與桌面管理

### Rectangle（視窗管理）
- https://rectangleapp.com/
- 快速排列視窗位置與大小
- 適合多螢幕與鍵盤流派使用者

### BetterDisplay（螢幕解析度控制）
- https://github.com/waydabber/BetterDisplay
- 用於高解析度螢幕、外接顯示器微調

---

## 六、系統工具與日常應用

### AppCleaner（必裝）
完整移除 App 及其 plist、快取與支援檔案，避免系統殘留垃圾。

- https://freemacsoft.net/appcleaner/

---

### Mole（免費開源 CLI 版系統清理工具）
免費開源的命令列系統清理與優化工具，整合 CleanMyMac、AppCleaner、DaisyDisk、iStat Menus 功能於單一執行檔。

- GitHub 專案：https://github.com/tw93/Mole
- 作者：tw93
- 安裝指令：`brew install mole`

#### 核心功能
- **深度清理（Deep Cleaning）**  
  掃描並移除快取、日誌、瀏覽器暫存檔案，可釋放數十 GB 空間
- **智慧卸載（Smart Uninstaller）**  
  徹底移除 App 及其 launch agents、偏好設定、隱藏殘留檔案
- **磁碟分析（Disk Insights）**  
  視覺化磁碟使用狀況、管理大型檔案、重建快取、刷新系統服務
- **即時監控（Live Monitoring）**  
  即時顯示 CPU、GPU、記憶體、磁碟、網路狀態，診斷效能問題
- **專案清理（Project Purge）**  
  清理開發專案中的 `node_modules`、`target`、`build`、`dist` 等建置產物

#### 特色
- **單一執行檔**：所有功能整合在一個 CLI 工具中
- **命令列介面**：適合鍵盤流與自動化腳本
- **免費開源**：MIT 授權，完全免費
- **安全設計**：支援 `--dry-run` 預覽變更，避免誤刪
- **操作日誌**：所有檔案操作記錄於 `~/.config/mole/operations.log`

#### 常用指令
```bash
mo                    # 互動式選單
mo clean              # 深度清理
mo uninstall          # 移除 App 與殘留檔案
mo optimize           # 重建快取與服務
mo analyze            # 視覺化磁碟分析
mo status             # 即時系統健康儀表板
mo purge              # 清理專案建置產物

mo clean --dry-run    # 預覽清理計畫
mo clean --debug      # 詳細操作日誌
```

#### 實際效果
使用者回報平均釋放 **20-100GB** 磁碟空間，清理範圍包含：
- 使用者 App 快取（平均 45GB）
- 瀏覽器快取（Chrome、Safari、Firefox，平均 10GB）
- 開發工具快取（Xcode、Node.js、npm，平均 23GB）
- 系統日誌與暫存檔（平均 4GB）
- App 專屬快取（Spotify、Dropbox、Slack，平均 8GB）

#### 安全建議
- 首次使用建議先執行 `mo clean --dry-run` 預覽
- 支援 whitelist 功能保護特定路徑
- 檔案刪除為永久性操作，請仔細檢查

#### 終端機相容性
- 推薦使用：Alacritty、kitty、WezTerm、Ghostty、Warp
- 已知問題：iTerm2 可能有相容性問題

#### 與 AppCleaner 比較
- **AppCleaner**：GUI 介面，適合一般使用者
- **Mole**：CLI 介面，功能更完整，適合進階使用者與自動化需求

---

### IINA（推薦播放器）
現代化 macOS 原生風格播放器。

- https://iina.io/
- 外觀佳、手勢與系統整合度高

#### 其他選擇
- **VLC**：格式支援最完整，但 UI 與 macOS 一致性較弱

---

### iStat Menus（付費）
即時監控系統狀態的選單列工具。

- https://bjango.com/mac/istatmenus/
- CPU / 記憶體 / 磁碟 / 電池 / 網路一目了然

#### 其他選擇
- **Stats**（免費開源）  
  https://github.com/exelban/stats  
  iStat Menus 的免費開源替代方案，提供 CPU / 記憶體 / 磁碟 / 電池 / 網路資訊監控
  - 安裝指令：`brew install stats`

---

### Ice（免費）
選單列管理工具，整理與隱藏雜亂 icon。

- https://github.com/jordanbaird/Ice
- Bartender 的免費替代方案

---

### AlDente（免費 / Pro 付費）
電池健康管理工具。

- https://apphousekitchen.com/
- 限制充電上限，適合長期插電使用

---

### CleanShot X（付費，一次買斷）
專業截圖與螢幕錄影工具。

- https://cleanshot.com/
- 遠勝 macOS 內建截圖功能

---

### BuhoCleaner（付費）
Mac 清理與維護工具。

- https://www.drbuho.com/buhocleaner
- 清垃圾、刪殘留、釋放空間

---

### Keka（免費）
壓縮 / 解壓縮工具。

- https://www.keka.io/
- 支援 zip、7z、rar、tar… 幾乎全包

---

### Amphetamine（免費，Mac 防休眠工具）
強大的 Mac 防休眠工具，可讓你的 MacBook 保持喚醒狀態。

- https://apps.apple.com/tw/app/amphetamine/id937984704?mt=12
- 功能特色：
  - 防止系統休眠與螢幕保護程式啟動
  - 可設定排程與觸發條件
  - 豐富的自訂選項與情境模式

#### 其他選擇
- **Caffeine**  
  https://www.caffeine-app.net/  
  輕量級防休眠工具，介面簡潔易用
- **KeepingYouAwake**  
  https://github.com/newmarcel/KeepingYouAwake  
  開源替代方案，基於 Caffeine 的現代化版本

---

## 七、開發與生產力工具（進階）

- **OrbStack**：Docker / VM 整合
- **1Password / Bitwarden**：密碼管理（安全性觀點分歧）
- **ScreenBrush**：簡報即時標註
- **BetterTouchTool**：觸控板手勢高度自訂

---

### 遠端檔案傳輸工具（SFTP / FTP Clients）

#### Termius（現代化 SSH/SFTP 客戶端）
現代化的 SSH / SFTP 客戶端，跨平台支援，UI 精緻、操作直覺。

- 官網：https://termius.com/
- 支援平台：macOS、Windows、Linux、iOS、Android
- GitHub CLI：https://github.com/termius/termius-cli

##### 特色
- **精緻 UI**：現代化介面設計，操作流暢直覺
- **雲端同步**：支援跨裝置同步連線設定（需登入帳號）
- **整合設計**：SSH 終端機與 SFTP 檔案管理整合於同一介面
- **多平台支援**：桌面版與行動版資料同步
- **團隊協作**：Pro 版支援團隊共享連線設定

##### 版本比較
- **免費版**：基本功能已堪用，單機使用足夠
- **Pro 版**：支援雲端同步、團隊協作、進階功能

##### CLI 工具
提供 `termius` CLI 工具，可透過指令列管理 SSH 連線：
```bash
brew install termius          # 安裝 CLI 工具
termius init                  # 初始化（登入、同步）
termius host --address localhost --label myhost
termius connect myhost
termius import-ssh-config     # 從 ~/.ssh/config 匯入
```

##### 適用情境
- 需要跨裝置同步 SSH/SFTP 連線設定
- 重視 UI/UX 體驗的使用者
- 團隊需要共享連線設定
- 行動裝置需要存取遠端伺服器

---

#### Cyberduck（免費開源 SFTP/FTP 客戶端）
輕量易用的檔案傳輸工具，Reddit 討論度最高的免費開源選擇。

- 官網：https://cyberduck.io/
- 授權：GPL 開源授權
- 社群：活躍的開源社群

##### 特色
- **多協定支援**：SFTP、FTP、FTPS、S3、WebDAV、Azure、Google Drive、Dropbox、OneDrive 等
- **拖放操作**：直覺的檔案拖放介面，適合入門使用者
- **開源免費**：完全免費，無功能限制
- **跨平台**：支援 macOS 與 Windows
- **書籤管理**：可儲存常用連線，快速存取
- **編輯器整合**：可設定外部編輯器直接編輯遠端檔案

##### 雲端服務整合
除了傳統 SFTP/FTP，Cyberduck 也支援主流雲端儲存服務：
- Amazon S3
- Google Cloud Storage
- Microsoft Azure
- Backblaze B2
- Dropbox、Google Drive、OneDrive

##### 使用建議
- 適合需要多協定支援的使用者
- 免費開源，無使用限制
- 社群活躍，更新頻繁
- 介面簡潔，學習曲線低

##### 與其他工具比較
- **vs FileZilla**：Cyberduck 介面更現代化，macOS 整合度更高
- **vs Transmit**（付費）：Transmit 功能更強大，但需付費
- **vs Termius**：Cyberduck 專注檔案傳輸，Termius 整合 SSH 終端機

---

#### 選擇建議

| 工具 | 價格 | 特色 | 適用對象 |
|------|------|------|----------|
| **Termius** | 免費/Pro 付費 | 現代化 UI、雲端同步、跨平台 | 重視體驗、需要跨裝置同步 |
| **Cyberduck** | 免費開源 | 多協定、輕量、社群活躍 | 預算有限、需要多協定支援 |
| **Transmit** | 付費 | 功能強大、macOS 原生、效能優秀 | 願意付費、追求最佳體驗 |
| **FileZilla** | 免費開源 | 功能完整、跨平台 | 傳統使用者、習慣 FileZilla |

---

## 八、Finder 與常用快捷技巧（高頻）

- `Cmd + Shift + G`：跳轉路徑
- `Cmd + Shift + .`：顯示 / 隱藏隱藏檔
- `Cmd + Option + V`：搬移取代複製
- 拖曳時按 `Cmd`：跨磁碟強制搬移
- 四指上滑：Mission Control

---

## 九、設定備份與長期維護

### dotfiles 管理
- https://hackmd.io/@lunzaizai/SJXGJa_4s
- 建議版本化 `.zshrc`、終端機設定、常用工具設定

#### GNU Stow
專為 dotfiles 管理設計的符號連結管理工具，透過建立 symlink 的方式整理設定檔。

- 官方網站：https://www.gnu.org/software/stow/
- Homebrew：https://formulae.brew.sh/formula/stow
- 安裝指令：`brew install stow`

**核心概念**
- **符號連結管理器（Symlink Farm Manager）**  
  原本設計用於在單一目錄樹下整齊組織軟體（如 `/usr/local`）
- **dotfiles 管理最佳實踐**  
  現代開發者主要用於跨機器管理設定檔（`.zshrc`、`.gitconfig`、`.vimrc` 等）

**工作原理**
1. 在 dotfiles 倉庫中以資料夾組織不同工具的設定檔
2. 使用 `stow` 指令建立符號連結到 home 目錄
3. 所有設定檔集中版本控制，方便同步與備份

**優點**
- **輕量極簡**：遵循 Unix 哲學，專注做好一件事
- **版本控制友善**：與 Git 完美搭配
- **跨平台支援**：適用於 Linux、macOS、BSD
- **無依賴性**：純 Perl 腳本，幾乎所有系統都能執行

**實務範例**
```bash
# 目錄結構
~/dotfiles/
  zsh/
    .zshrc
  git/
    .gitconfig
  vim/
    .vimrc

# 使用 stow 建立連結
cd ~/dotfiles
stow zsh    # 建立 ~/.zshrc -> ~/dotfiles/zsh/.zshrc
stow git    # 建立 ~/.gitconfig -> ~/dotfiles/git/.gitconfig
stow vim    # 建立 ~/.vimrc -> ~/dotfiles/vim/.vimrc
```

**使用建議**
- 搭配 Git 進行版本控制
- 可與 Oh My Zsh、Homebrew 設定一併管理
- 適合需要在多台機器間同步開發環境的使用者

**其他選擇**
- **chezmoi**：功能更豐富，支援範本化與加密（已於 Issue #4 討論）
- **yadm**：基於 Git 的 dotfiles 管理工具
- **rcm**：ThoughtBot 開發的 dotfiles 管理工具

---

## 十、延伸閱讀與共筆

- What's on my Mac  
  https://wylin.tw/pages/whats-on-my-mac/

- Mac 常用快捷鍵大全  
  https://share.google/gFUWcXYJ87QH9tMsf

- 社群共筆（Mac 使用技巧彙整）  
  https://hackmd.io/@FVOecMgySGqHx8oqmC3ROQ/rk_Qlo4wbx/edit

---

## 結語

**Mac 的學習曲線不在於記住所有快捷鍵，而在於建立「符合自己習慣的工作流」。**  
建議分階段導入工具，先解決不順手的地方，再逐步深化客製化程度。
