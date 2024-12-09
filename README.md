# 社群媒體系統

實作一個簡易社群媒體平台，功能需包含以下：

## 1. 註冊功能
- 使用者可以透過註冊功能註冊帳號，以 email 進行註冊與登入。

## 2. 登入驗證功能
- 系統需實作身份驗證功能，以確保只有登入的使用者可以發文或留言。

## 3. 發文功能
- 新增發文。
- 列出所有發文。
- 編輯或刪除發文。

## 4. 留言功能
- 使用者可以針對發文新增留言。

## 5. 系統架構要求
- 使用 Web Server + Application Server + 任一關聯式資料庫的三層式架構。
- 後端依照需求設計展示層、業務層、資料層以及共用層。

## 6. 技術要求
- 使用 React.js 做為前端技術。
- 使用 Spring Boot 搭建相關應用程式。
- 使用 RESTful API 風格建立後端服務。
- 使用 Maven 做為專案建立的工具。
- 透過 Stored Procedure 存取資料庫。
- 需同時異動多個資料表時，請實作 Transaction，避免資料錯亂。
- 資料庫的 DDL 和 DML 請存放在專案下的 `\DB` 資料夾內提供。
- 需防止 SQL Injection 以及 XSS 攻擊。

---

## 基礎資料表與資料範例

### 1. User 使用者
| 欄位名稱      | 說明                                                    |
| ------------- | ------------------------------------------------------- |
| User ID       | 使用者 ID (Primary Key)                                 |
| User Name     | 使用者名稱                                              |
| Email         | 使用者電子郵件                                          |
| Password      | 密碼請加鹽(salt)並經雜湊(Hash)後儲存，避免明碼外洩       |
| Cover Image   | 封面照片 (非必要欄位)                                   |
| Biography     | 使用者的自我介紹                                        |

### 2. Post 發文
| 欄位名稱      | 說明                                                    |
| ------------- | ------------------------------------------------------- |
| Post ID       | Primary Key                                             |
| User ID       | Foreign Key to User                                     |
| Content       | 發佈文章內容                                            |
| Image         | 圖片 (非必要欄位)                                       |
| Created At    | 發佈時間                                                |

### 3. Comment 留言
| 欄位名稱      | 說明                                                    |
| ------------- | ------------------------------------------------------- |
| Comment ID    | 留言 ID (Primary Key)                                   |
| User ID       | 使用者 ID (Foreign Key)                                 |
| Post ID       | Post ID (Foreign Key)                                   |
| Content       | 留言內容                                                |
| Created At    | 留言時間                                                |
