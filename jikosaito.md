```uml
@startuml
opt 未登録
ユーザー -> webサーバー:会員登録情報
webサーバー -> DBサーバー:会員登録情報
DBサーバー -> DBサーバー:会員登録情報
alt 認証成功
DBサーバー -> webサーバー:登録完了
webサーバー -> ユーザー:登録完了表示
else 認証失敗
DBサーバー -> webサーバー:登録失敗(エラー)
webサーバー -> ユーザー:登録失敗(エラー)表示
end
end

webサーバー -> ユーザー:ログイン画面
ユーザー -> webサーバー:会員情報
webサーバー -> DBサーバー:会員情報
DBサーバー -> DBサーバー:会員情報
alt 照合成功
DBサーバー -> webサーバー:トップページ
webサーバー -> ユーザー:トップページ表示
else 照合失敗
DBサーバー -> webサーバー:エラー
webサーバー -> ユーザー:エラー表示
end

loop
ユーザー -> webサーバー:商品一覧
webサーバー -> DBサーバー:商品一覧
DBサーバー -> DBサーバー:商品一覧
DBサーバー -> webサーバー:商品一覧ページ
webサーバー -> ユーザー:商品一覧ページ表示
ユーザー -> webサーバー:商品検索
webサーバー -> DBサーバー:商品検索
DBサーバー -> DBサーバー:商品検索条件
DBサーバー -> webサーバー:検索結果
webサーバー -> ユーザー:検索結果表示
ユーザー -> webサーバー:商品詳細
webサーバー -> DBサーバー:商品詳細
DBサーバー -> DBサーバー:商品詳細 
DBサーバー -> webサーバー:商品詳細ページ
webサーバー -> ユーザー:商品詳細ページ表示
opt カートに入れる
ユーザー -> webサーバー:商品購入詳細
webサーバー -> DBサーバー:商品購入詳細
DBサーバー -> DBサーバー:商品購入詳細保管
DBサーバー -> webサーバー:カート内追加
webサーバー -> ユーザー:カート内表示
end
ユーザー -> webサーバー:トップページ
webサーバー -> DBサーバー:トップページ
DBサーバー -> DBサーバー:トップページ
DBサーバー -> webサーバー:トップページ
webサーバー -> ユーザー:トップページ表示
end
@enduml
```
