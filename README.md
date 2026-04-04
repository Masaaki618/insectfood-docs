# 昆虫食初心者ガイド

![Flutter](https://img.shields.io/badge/Flutter-3.x-02569B?logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-3.x-0175C2?logo=dart&logoColor=white)
![Go](https://img.shields.io/badge/Go-1.x-00ADD8?logo=go&logoColor=white)
![Claude](https://img.shields.io/badge/Claude-Haiku_4.5-FF6B35?logo=anthropic&logoColor=white)
![TiDB](https://img.shields.io/badge/TiDB-Cloud-E94E1B?logo=tidb&logoColor=white)
![Cloud Run](https://img.shields.io/badge/Google_Cloud_Run-4285F4?logo=googlecloud&logoColor=white)

昆虫食に興味があるけど、何から始めたらいいかわからない初心者向けの診断アプリです。
3つの耐性スコアをもとにAIがあなたにぴったりの昆虫食をレコメンドします。

---

## このアプリについて

2022年に Ruby on Rails で開発した昆虫食診断サービスをベースに、AIによるパーソナライズされたレコメンドを実現したくリニューアルしました。

> 📝 前バージョンの開発記事：[【個人開発】少しでも昆虫に興味をもって食べてみたくなるような診断サービスを作った。](https://qiita.com/masaaki_618/items/13efc16f16164e8ac89a)
>
> 📋 前バージョンの設計書：[Insect-Food アプリケーション概要（HackMD）](https://hackmd.io/@masaaki-618/SJUZV_l6q)

---

## こんな人におすすめ

- 昆虫食に興味はあるけど何から始めたらいいかわからない
- 虫は苦手だけど話のネタに試してみたい
- 健康・環境に興味がある

---

## MVP機能

| 機能 | 概要 |
|------|------|
| 昆虫食診断 | 3つの耐性カテゴリから各2問・計6問のはい/いいえ形式で回答 |
| AIレコメンド | 診断スコアをもとにClaude Haiku 4.5がぴったりの昆虫食とコメントを自動生成 |
| 昆虫一覧 | 登録されている10種類の昆虫を一覧表示 |
| 昆虫詳細 | 味・食感・レーダーチャート・AIコメントを表示 |

---

## 3つの耐性スコアとは

診断では以下の3カテゴリを2問ずつ測定し、それぞれ0〜2点のスコアを算出します。
このスコアの組み合わせをAIに渡すことで、あなたに最適な昆虫食をレコメンドします。

| カテゴリ | 測定内容 |
|---------|---------|
| 👁 見た目への耐性（visual） | 虫の見た目に対してどれだけ抵抗がないかを測ります。形がそのまま残っている食べ物でも食べられるかどうかが判断基準です |
| 🤚 食べる勇気（physical） | 実際に虫を食べる行動にどれだけ踏み出せるかを測ります。口に入れる・噛むという行為への心理的ハードルを評価します |
| 💪 挑戦する気持ち（mental） | 新しい食体験に挑戦しようという気持ちがあるかを測ります。未知の食材への好奇心・チャレンジ精神を評価します |

---

## AIによる自動レコメンド

診断完了後、3つのスコアをClaude Haiku 4.5に送信し、以下を自動生成します。

- **おすすめ昆虫食** → スコアに合った難易度・種類の昆虫をレコメンド
- **パーソナライズコメント** → あなたのスコアに合わせた80〜100文字のひとことコメント

AIがリアルタイムで生成するため、同じスコアでも毎回異なるコメントが返ってきます。

---

## 画面紹介

> ⚠️ 以下の画像はBolt.newで作成したプロトタイプです。実際のアプリのデザインとは異なります。

### トップ画面
アプリの説明・診断の概要・診断開始ボタン

<img width="400" alt="トップ画面" src="https://github.com/user-attachments/assets/d07e073e-2d1e-4446-b4f0-8eed302ffa1d" />

---

### 診断フロー画面
6問をはい/いいえで回答。プログレスバーで進捗を表示

<img width="400" alt="診断フロー画面" src="https://github.com/user-attachments/assets/27fd0f2a-eb9d-4a54-b36a-3a4895d66c9e" />

---

### 診断結果画面
AIがレコメンドした昆虫・コメント・詳細への導線を表示

<img width="400" alt="診断結果画面" src="https://github.com/user-attachments/assets/94de2962-204a-46d8-bc68-f5d98328f928" />

---

### 昆虫一覧画面
登録されている10種類の昆虫をカード形式で一覧表示

<img width="400" alt="昆虫一覧画面" src="https://github.com/user-attachments/assets/235088dd-78e3-49c2-92e9-03ad5e3a0dcc" />

---

### 昆虫詳細画面
昆虫の味・食感・説明・AIコメント・味覚レーダーチャートを表示

<img width="400" alt="昆虫詳細画面" src="https://github.com/user-attachments/assets/6c13b202-3ed5-478c-a3bf-84eb2e74d81c" />

---

## 今後追加予定の機能

| 機能 | 概要 |
|------|------|
| 認証・ユーザー管理 | ログイン・アカウント管理 |
| お気に入り機能 | 気になった昆虫をブックマークして後で確認 |
| レビュー機能 | 食べた昆虫の感想・レビューを投稿・閲覧 |
| SNSシェア機能 | 診断結果や昆虫情報をSNSで共有 |
| 管理画面 / CMS拡張 | 昆虫データの追加・更新フローの整備 |

---

## 技術スタック

| カテゴリ | 技術 |
|---------|------|
| フロントエンド | Flutter / Dart |
| 状態管理 | Riverpod |
| HTTP通信 | dio |
| 画面遷移 | go_router |
| グラフ | fl_chart |
| バックエンド | Go / Gin（Cloud Run） |
| データベース | TiDB Cloud（MySQL互換） |
| AI | Claude Haiku 4.5 |

---

## ドキュメント

| ドキュメント | ファイル |
|------------|--------|
| 要件定義 | [01_requirements.md](./01_requirements.md) |
| アーキテクチャ | [02_architecture.md](./02_architecture.md) |
| DB設計 | [03_database.md](./03_database.md) |
| API設計 | [04_api.md](./04_api.md) |
| サイトマップ | [05_sitemap.md](./05_sitemap.md) |
