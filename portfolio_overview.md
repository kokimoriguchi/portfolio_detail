# オリジナルプロダクト

## 概要

### 【シフト管理アプリ】

1. 一言サービスコンセプト（サービスのキャッチコピーを一言で）<br />
   毎日のシフトの抜け漏れを防ぐ！！

2. 誰のどんな課題を解決するのか？<br>
   シフト制の職場での勤怠管理を担当している社員(マネージャー)をメインターゲットに管理コストを低減する。併せてスタッフ(ユーザ)の労力軽減も進める。

3. なぜそれを解決したいのか？<br>
   前職ではシフト提出が紙で行われており、マネージャーは全スタッフの紙を何度も確認しシフトに空きがないよう調整しながらエクセルにまとめ確認しまた調整といった作業を行なっていた。<br>
   その無駄を解決し現場でしかできない意義のある時間を増やしたい。<br>
   併せて、スタッフの月末に職場に提出だけしにくる労力、印刷し張り出されたタイミングで写真を撮り自身のシフトを確認する不便さ、また更新された時の認識不足のズレも併せて解決したい。

4. どうやって解決するのか？<br>
   提出フォーマット及びシフト確認画面を管理する。
   シフト調整するマネージャーが何十枚もの紙を見比べながらエクセルに打ち込む必要をなくすために提出自体をデータで行う。

### 課題と現状

#### マネージャーサイド

- 勤務終了後 1-2 週間ほどかけ少しづつシフト作成している(勤務時間外や休日に作成している)
- アルバイト含めると 40 人を超える従業員のシフトの紙を全て確認する手間
- 確定したシフトは 1 ヶ月分 40 人の名前と出勤日が書かれた A3 で張り出されるので字が小さく見ずらい。
- 繁忙期などの時間帯別での各カテゴリーの場所に人員配置できているかの確認でその紙では見づらいので単日のシフト表(31 枚)を全て印刷し確認している効率の悪さ
- 紙での提出のないアルバイトに連絡を 1 人づつ取らないといけない
- 誰がどの加工技術を持っているのかが不明確なので、各カテゴリーの加工できる人がいない日がある。
- Excel を思い通りに使いこなせるわけではないので縦軸の名前の部分を固定できず月末の 31 に向かっていくと名前が見えず場所を覚えながら日付と出勤日を見ていく必要がある。

#### スタッフサイド

- 忙しくても紙なので月末までに記述した紙を提出しにこなければならない
- 確定したシフトは 1 ヶ月分 40 人の名前と出勤日が書かれた A3 で張り出されるので字が小さく見ずらい。
- 上記に付随して下の欄の名前の人ほど日付と合わせながら見るのが大変。
- 同じく月の後半になると左側に記述のある自身の名前と合わせて見るのが大変。

### 技術面と参考リンク

Frontend は全て React で行い基本シングルページネーションを意識して作成したい。
Backend は Rails の API モードにて実行し React に適宜データの受け渡しを行うようにする。
下記サイトに感銘を受けプログラミングを学ぶきっかけになった記事なので、大いに参考にしてしまっており良くなければ変更したい。
[学生の作ったシフトアプリ](https://zenn.dev/pae_26/articles/dba5403eca50f0)

### メイン機能

- マネージャー画面とスタッフ画面でログインによる分岐で表示画面およびハンバーガーメニュー内変更
- マネージャーによるシフトの管理及び確認
- スタッフによる出勤可能日の提出
- 確定シフトの確認
- 各スタッフには可能加工技術を登録でき、その加工できる人がいない日は表示が出る。

<details><summary>機能要件</summary>

MVP として 1 から 6 までの機能でまずは作成を目標にしています。

- 1. スタッフが画面のカレンダーから日付を選択し出勤可能なシフトの時間帯をデータとして送信できる
- 2. マネージャーはスタッフから送信されたシフトデータをマネージャー画面の仮シフト一覧にて全スタッフの出勤可能日を確認できる
- 3. マネージャーはスタッフの出勤可能日を確定・変更・削除ができる
- 4. マネージャーは確定したシフトを確定シフトとして全スタッフが閲覧可能の状態にして公開ができる
- 5. 全ページの company name の部分を store テーブルの name カラムに変更する
- 6. トップページからログインができる
- 7. 全ページ共通のハンバーガーメニューを作成しクリックで開くことでお問い合わせ、変更依頼、お知らせの機能を使うことができる。
- 8. 各ユーザーは確定したシフトに対してハンバーガーメニュー内の変更依頼からシフトの変更をマネージャーに依頼できる。プルリクエストのイメージ
- 9. マネージャーは変更依頼を受け取ると確定シフト画面からシフトの update ができる。
- 10. 上記の update された場合はハンバーガーメニュー内のお知らせ一覧から各ユーザーは確認できる
- 11. 確定したシフトの CSV 出力

</details>

<details><summary>非機能要件</summary>

- 1. ログインに関して cookie にてパスワードを保存してログインを簡単にできる
- 2. ユーザーは基本ケータイ、マネージャーは基本パソコンでこのアプリを使う想定なのでレスポンシブ対応
- 3. 個人情報を扱うのでセキュリティ面の確保
- 4. デプロイの仕組みとして、GitHub の main ブランチにマージしたら自動デプロイされる機能は盛り込みたい。(GitHubActions にて CI/CD 実装)
- 5. マネージャーは各スタッフのシフトデータ等を取得することがあるため全データを都度取得することのないように N±1 問題を意識しパフォーマンスの低下を引き起こさない様に実装する。
- 6. ESLint,Prettier による Front 側の静的解析、rails 側の Minitest によるコードの品質を保つ。

</details>

<details><summary>ワイヤーフレームとER図</summary>

## トップページ（店舗ログイン）

このページが一番初めに表示されるようにする。
ここで店舗番号を打ち込むことで登録されている店舗にログインできる。
新たに店舗作成する場合は店舗 number 入力画面下クリックで新規作成に移動。
<img src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2741017/4b2526a9-a521-f7a3-ce92-1b410fcfda5d.png">

下記新規店舗登録イメージでここで新しい店の名前と番号、マネージャーを作成する
<img src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2741017/eba40005-335d-1050-4bd6-ae9e85fffff4.png">

## ユーザログイン入力画面

店舗ログインするとこの画面に移動
ここで社員番号と自分で決めたパスワード打ち込むとスタッフもしくはマネージャーの画面にログインできる。
マネージャーの場合は下のマネージャーはこちらからボタンを押すことでマネージャー用のパスワード入力画面にいく。
<img width="" src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2741017/59f76eac-f2ef-d9c3-aae7-e38afafb9c33.png">

## マネージャースタッフ共通のログインした場合のトップ画面・確定シフト一覧（パソコン表示）

ログイン後今月の確定シフト一覧が大きく出る。※確定していない場合は今月分の仮シフト一覧が出る。
下のスライドバーで横移動でき上段の日付とスキル・部門と氏名は固定されている。
ハンバーガーメニューの中身はマネージャーかスタッフかで変わる
<img src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2741017/81110b62-b03a-6fb5-37f0-363b07b20696.png">

## 管理者画面(仮シフト一覧：SHIFT PAGES)

マネージャー画面のハンバーガーメニュー内からアクセス可能。
ここにシフト提出されればそのデータに基づいて可能時間を入れていくことができる。
⚪︎ になっている部分はこの日に出勤できる時間があるサイン(ユーザー画面からの送信でこの日付に時間帯記述されている意味)でこの部分をクリックするとプルダウンでその時間帯を指定できる。
× になっているところは出勤できない日として登録されているので何もできない。
確定ボタンを押せば現状登録されているカレンダーがユーザー画面に表示される様になる。
一時保存ボタンはユーザー画面には表示されず管理者として再度ログインしてこの画面に戻ってきても同じ状態を保つ様にする。
部門と名前の表示は固定でスクロールバーで日付だけ流せる様にしたい。
※アルファベットは無しにし時間表示に固定。true・false で出勤可否はマルバツで表示する。
<img width="" src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2741017/b278d4ca-3588-0270-9578-f9d823fc4f42.png">

丸になっているところを押すと下記イメージのようにモーダル表示で時間をプルダウン的に出勤時間と退勤時間入れることができる
時間を合わせて送信ボタンを押すと先ほど選んだ時間に丸になっていた部分が変わる。
また同様にスキルの部分も
<img src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2741017/baaa544b-c70c-4d47-b666-41e9de03c919.png">

## ハンバーガーメニューイメージ

管理者の場合はこの中に create account があり新規スタッフの登録ができる。また仮シフトはハンバーガーメニュー内の SHIFT ボタン押すことで表示して登録等ができる。
スタッフの場合は request ボタンに変わり変更依頼ができる、また SHIFT ボタンは次月の自身のシフト提出画面に遷移するボタンになっている。
<img src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2741017/bc1ff860-b1a0-3f9a-1e9f-e384c9a53e4e.png">

## ユーザー画面

スタッフログイン後は今月の自分の出勤日入りの縦型カレンダーの表示で下記のように表示される。(パソコンではなくケータイでの使用想定)
ハンバーガーメニューからシフト提出画面に行くと自分の来月の出勤予定を提出する画面になる。
<img width="" src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2741017/4b37b25b-fbee-45d4-29e8-8d74870dc875.png">

日付をクリックするとモーダル表示で出勤時間と退勤時間をプルダウン的に選択できるのでそこで選ぶ。何も選ばれていない日付は送信後デフォルトで × になる。
日付内は出勤時間と退勤時間が上下で並ぶ感じで小さめに表記。当日分の予定はカレンダー下に大きく表示する。
下記モーダルイメージ
<img src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2741017/fd527d1b-b2de-58f2-79aa-797866531a97.png">

## ER 図

<img src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2741017/298e20b1-b220-88fc-cd1b-7f983a5e622e.png">

</details>

<details><summary>サイトマップ</summary>
<img width="" src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2741017/32667234-3732-191d-91e8-a17d3a905b4d.png">
</details>

<details><summary>追加機能</summary>

### 追加機能

- 問い合わせ機能<br>
  ハンバーガーメニューの中に問い合わせ機能を入れる
  問い合わせ内容や改善して欲しい点を自分にメールを送ることができる機能

- 出勤可能日変更依頼<br>
  シフト提出者側は基本的には提出したシフトの変更は自由にできないが GitHub のプルリクエストのように変更依頼を出すことができる。<br>
  管理者側で確認された場合は確定シフトに変更を加えてもらう。<br><br>

- お知らせ機能<br>
  ハンバーガーメニューを作りそこにお知らせ機能を入れる。
  そこを押すと確定シフトが更新されたことや、出勤日変更依頼が届いていることなどが確認できる。

- 各従業員のスキルレベル表示<br>
  各従業員に属性としてスキルレベルを持たせ（管理者画面でしか確認できない）単日のスキルレベル合計が設定した数値よりも低ければ日付部分の色を変更しスキル不足を表示する。<br>※前職は 1000 坪以上ある大型店だったが人員不足を補うほどの募集が集まる地域でなかったためスキルの高い人員を適切に配置することが重要だったためスキルを可視化できるようにしたい<br><br>

- 店舗ごとのアカウント作成<br>
  店舗ごとのログイン機能を持たせ何店舗でも管理者と店舗従業員を持ったテーブルを作れるようにする<br><br>

- CSV 出力<br>
  確定したシフトを CSV 出力可能にし既存のシフト一覧のエクセルに貼り付け可能にする。<br><br>

- Gpt4 によるシフト最適化<br>
  Gpt4 の API を入れ込み各従業員の出勤可能日が提出され次第管理者画面にて API を叩くボタン設置し各日程の最適人数を当てはめてくれる機能<br><br>

</details>

<details><summary>ディレクトリ構成</summary>

## ディレクトリ構成

````
ShiftApp
├── backend
│   ├── app
│   │   ├── api/v1
│   │   │   ├── approve_months_controller.rb
│   │   │   ├── confirm_shifts_controller.rb
│   │   │   ├── employee_shifts_controller.rb
│   │   │   ├── employees_controller.rb
│   │   │   ├── manager_shifts_controller.rb
│   │   │   ├── managers_controller.rb
│   │   │   ├── sessions_controller.rb
│   │   │   └── stores_controller.rb
│
├── frontend
│   ├── public
│   │   ├── index.html
│   │   └── manifest.json
│   ├── src
│   ├── App.css
│   ├── App.js
│   ├── components
│   │   ├── data
│   │   │   └── Date.jsx
│   │   ├── hooks
│   │   │   ├── Alert.jsx
│   │   │   ├── Auth.jsx
│   │   │   ├── Axios.jsx
│   │   │   ├── CalenderRender.jsx
│   │   │   ├── ConfirmShift.jsx
│   │   │   ├── ConfirmationModal.jsx
│   │   │   ├── DarkModeButton.jsx
│   │   │   ├── EditShiftUpdate.jsx
│   │   │   ├── EmployeeCreateHook.jsx
│   │   │   ├── FadeInHook.jsx
│   │   │   ├── GetConfirmMonth.jsx
│   │   │   ├── GetShiftDataHook.jsx
│   │   │   ├── GetSubmitMonth.jsx
│   │   │   ├── HeaderMoveButton.jsx
│   │   │   ├── HomeMoveButton.jsx
│   │   │   ├── InputForm.jsx
│   │   │   ├── InputFromButton.jsx
│   │   │   ├── LoginHook.jsx
│   │   │   ├── ManagerCreateHook.jsx
│   │   │   ├── Modal.jsx
│   │   │   ├── ModalManager.jsx
│   │   │   ├── NavigateButton.jsx
│   │   │   ├── StoreCreateHook.jsx
│   │   │   ├── SubmitFlexButton.jsx
│   │   │   ├── SubmitShift.jsx
│   │   │   ├── ToLocalStorageHooks.jsx
│   │   │   ├── useDarkMode.jsx
│   │   │   └── useGetShiftDataHook.jsx
│   │   └── pages
│   │       ├── Calender.jsx
│   │       ├── ConfirmShiftCalender.jsx
│   │       ├── EmployeeCreate.jsx
│   │       ├── EmployeeLogin.jsx
│   │       ├── EmployeeTop.jsx
│   │       ├── Footer.jsx
│   │       ├── Header.jsx
│   │       ├── Home.jsx
│   │       ├── ManagerCreate.jsx
│   │       ├── ManagerLogin.jsx
│   │       ├── ManagerTop.jsx
│   │       ├── StoreCreate.jsx
│   │       └── SubmitCalender.jsx
│   ├── index.css
│   └── index.js
└── tailwind.config.js```

</details>

<details><summary>システム構成図</summary>

<img src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2741017/cd52536a-c5ab-3dcf-6565-e225db5d0e2c.png">

</details>

<details><summary>使用予定技術</summary>

## 使用予定技術

backend

- Ruby 3.1.0
- Ruby on Rails 6.1.5(API モード)

frontend

- React 18.2.0(node 14.17.1)

infrastructure

- Docker 23.0.5
- AmazonWebServices

database

- MySQL 8.0

その他

React 側の追加ライブラリ/パッケージ

- tailwind
- react-router-dom
- axios
- ESLint
- prettier

Rails 側の追加 Gem

- rack-cors
- dotenv-rails
- rubocop
- bcrypt
- jwt

</details>
````
