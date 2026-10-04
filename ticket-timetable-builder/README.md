# イベントタイムテーブル作成

TicketDiveのイベントURLを読み込み、イベント画像から出演者・時刻を確認して、Excel形式のタイムテーブルを作るツールです。

## 利用

公開版: https://event-timetable-builder.sengoku-akb.chatgpt.site

1. TicketDiveのイベントページURLを入力します。
2. 読み込まれたイベント情報と画像を確認します。
3. 画像から文字を読み取り、出演者名と時間を整えます。
4. ExcelファイルをダウンロードしてGoogleスプレッドシートで開きます。

画像認識結果は必ず確認してください。イベントページから取得できない項目や正確な出演時刻は、表で手入力できます。

## ソース

`worker/index.js` はSites上で動くWorkerです。HTML画面とTicketDiveページの取得処理を含みます。GitHub PagesはWorker APIを実行しないため、このWorkerをそのままPagesへ配置してもURL読み込みは動きません。公開版は上記URLで利用できます。

画像OCRとExcel出力には、Tesseract.jsとxlsx-js-styleをCDNから読み込みます。
