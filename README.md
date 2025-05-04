# 🏠 HomiFinder
HomiFinder 是一個租屋平台專案，旨在提供房東與租客一個簡單易用的房屋刊登與搜尋平台。使用者可以瀏覽、上傳、管理房源，並透過地圖與篩選功能快速找到理想的租屋資訊。

## 專案頁面
![Virtual Reality](./client/readme_assets/home_page.png)

## 專案架構
本專案採用前後端分離架構：
```bash
HomiFinder/
├── client/   # 前端：Next.js + Tailwind CSS
└── server/   # 後端：Node.js + Express + Prisma
```

## 功能特色
- 房源搜尋：依據地點、價格、房型等條件篩選房源

-  圖片上傳：支援多張圖片上傳，並儲存至 AWS S3

-  地圖整合：整合 Mapbox，顯示房源位置

-  使用者認證：透過 AWS Cognito 進行登入與註冊

-  租賃管理：房東可管理房源，租客可提交申請

-  後台管理：房東可查看申請紀錄與租賃狀態

## 技術棧(Tech Stack)
### 前端（client）
- Next.js

- Tailwind CSS

- Mapbox GL JS

- React Hook Form

- React Toastify

- AWS Amplify（用於 Cognito 認證與 S3 上傳）

### 後端（server）
- Node.js

- Express

- Prisma ORM

- PostgreSQL

- AWS RDS

- AWS S3

- PM2（用於部署與監控）

## 開發與部署
### 前端啟動
```bash
cd client
npm install
npm run dev
```
### 後端啟動
```bash
cd server
npm install
npx prisma generate
npx prisma migrate dev
npm run dev
```
### 使用 PM2 部署後端
```bash
pm2 start ecosystem.config.js
```

## 環境變數設定
請在 client/.env 與 server/.env 中設定以下環境變數：
### client/.env
```bash
NEXT_PUBLIC_MAPBOX_TOKEN=your_mapbox_token
NEXT_PUBLIC_S3_BUCKET_URL=https://your-bucket.s3.amazonaws.com/
NEXT_PUBLIC_COGNITO_USER_POOL_ID=your_user_pool_id
NEXT_PUBLIC_COGNITO_CLIENT_ID=your_client_id
```
### server/.env
```bash
DATABASE_URL=postgresql://user:password@host:port/database
AWS_REGION=ap-northeast-1
AWS_ACCESS_KEY_ID=your_access_key
AWS_SECRET_ACCESS_KEY=your_secret_key
S3_BUCKET_NAME=your_bucket_name
```

## 開發者
GitHub: [@MinJyun](https://github.com/MinJyun)

## 授權
本專案採用 MIT 授權。