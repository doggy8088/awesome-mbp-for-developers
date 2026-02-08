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

---

### Ice（免費）
選單列管理工具，整理與隱藏雜亂 icon。

- https://github.com/jordanbaird/Ice
- Bartender 的免費替代方案

---

### PasteNow（付費，一次買斷）
進階剪貼簿管理工具。

- https://pastenow.app/
- 可回溯所有複製過的文字、程式碼、圖片

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

## 七、開發與生產力工具（進階）

- **OrbStack**：Docker / VM 整合
- **1Password / Bitwarden**：密碼管理（安全性觀點分歧）
- **ScreenBrush**：簡報即時標註
- **BetterTouchTool**：觸控板手勢高度自訂

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
