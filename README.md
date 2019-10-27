# rione_msgs for ros2

このメッセージ群はRione内で円滑にコマンド送信等を行うためのものです.

## 種類
Command.msg
- command : string
> 実行して欲しいコマンドを格納
- content : string
> 実行時に必要なデータを格納
- sender : string
> 送信元を格納

## メモ
現在はSPR作成時に出てきた問題点をもとに考えた最小限のデータ構造
