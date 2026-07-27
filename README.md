# S-ERP Updates

## 專案介紹

本 Repository 是 S-ERP 的公開更新通道 Repository，預定用於提供 Windows 更新所需的發布資訊與檔案。

目前它**不是 S-ERP 應用程式的原始碼 Repository**。S-ERP 原始碼維護於另一個未公開的 Repository；本 Repository 無法用來了解該應用程式的完整架構、功能完成度或開發進度。

目前 Repository 以 `manifest.json` 提供最新正式更新資訊；完整 Windows Release ZIP 仍只放在對應 GitHub Release 資產，不納入 Git 追蹤。

## Repository 目前內容

| 類別 | 目前狀態 |
| --- | --- |
| 文件 | `README.md`（本檔） |
| S-ERP 原始碼 | 未包含 |
| Python 程式 | 未包含 |
| 設定檔（JSON／YAML） | 未包含 |
| 更新清單 | `manifest.json`（目前版本、下載網址、SHA-256、說明與發布時間） |
| Assets | 未包含 |
| GitHub Actions 工作流程 | 未包含 |
| Build Script 或 requirements 檔 | 未包含 |
| 發布包、Python Runtime、EXE | 未包含於 Git 追蹤檔案 |

## Release 說明

Repository 的 Git 檔案與 GitHub Release 資產是不同的發布位置：

| 項目 | 目前可確認狀態 |
| --- | --- |
| Repository 檔案 | `README.md`、`manifest.json` |
| GitHub Release 資產 | 不屬於 Git 追蹤檔案；完整 Windows ZIP 與同內容 `manifest.json` 由 GitHub Release 提供 |
| Python Runtime | 未包含於 Repository |
| EXE | 未包含於 Repository |
| Windows 更新包 | 未包含於 Repository |
| 使用者安裝或執行所需檔案 | 未包含於 Repository |

若日後透過 GitHub Release 發布更新包，實際提供的檔名、內容與版本必須以該 Release 的資產清單為準；本 README 不預先宣告尚未存在的發布內容。

## 目前更新機制

S-ERP 使用其 `version.json` 指向的 GitHub Release latest-download `manifest.json` 檢查更新。Manifest 提供最新版、完整 ZIP 下載網址、SHA-256、更新說明與發布時間；客戶端僅在使用者確認後下載並驗證 ZIP。完整更新套用、備份與回復行為由 S-ERP 原始碼 Repository 的 Launcher／Updater 實作，不在本 Repository 重複保存原始碼。

## 目前專案架構

```text
S-ERP-Updates/
├── README.md
└── manifest.json
```

`.git/` 為本機 Git 管理資料，不是專案發布內容。

## 目前開發狀態

| 項目 | 狀態 |
| --- | --- |
| 公開更新通道 Repository | 已建立 |
| Repository 說明文件 | 已提供 |
| 更新清單 | 已提供 `manifest.json` |
| 完整更新 ZIP | 由 GitHub Release 資產提供，不納入 Git |
| 自動化發布或建置設定 | 尚未包含於 Repository |
| S-ERP 應用程式原始碼 | 不在此 Repository |

## Developer Notes

- 此 Repository 的目的，是作為 S-ERP 公開更新發布通道，而非應用程式開發 Repository。
- `manifest.json` 是本更新通道的最新更新資訊來源；Release 前必須使其版本、ZIP 檔名、下載網址與 SHA-256 一致。
- 本 Repository 不包含更新程式實作；套用、備份與回復行為必須由 S-ERP 原始碼 Repository 的 Launcher／Updater 確認。
- GitHub 在此 Repository 用於託管更新資訊與 Release 資產；目前未發現已提交的發布自動化設定。

## 驗證範圍

本 README 的內容僅依目前 Git 追蹤的 Repository 檔案重新檢查後撰寫。它不以歷史提交、外部專案、未追蹤檔案或一般專案慣例推測功能與發布內容。
