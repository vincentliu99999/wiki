# [Travis](https://docs.travis-ci.com/)

## 初心者該懂的事

### 簡介

持續整合(Continuous Integration)，通常叫做 CI，目的是讓你可以很頻繁的合併微小的變更，持續透過建置、測試、部屬、通知，打造快樂又健康的軟體

建置時，Travis 會 clone 你的 GitHub repository 到全新的虛擬環境，進行一系列的建置與測試任務，`broken`: 任務失敗，`passed`: 沒有任務失敗

### 特殊名詞

- phase: 順序性的任務，install > script > deploy
- job: 虛擬環境上的任務，如果 `script` 階段的 return code 不是 0 就是個失敗的任務
- build: 一群任務，比如測試各種版本的程式語言
- stage: TODO

### 建置中斷

- errored: `before_install`, `install`, `before_script` 階段的 return code 不是 0
- failed: `script` 階段的 return code 不是 0，任務會繼續下去
- canceled: 使用者中斷