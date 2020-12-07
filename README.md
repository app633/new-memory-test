# MemoryTest3.1

変更点（プログラム）
・QuizActivityにおいて、画面回転等で急にActivityが破壊されてもデータをBundleへ入れて保存し
　復帰時に同じ状態に戻すようにした。
　ただし、マニフェストxmlファイルで「android:screenOrientation="portrait"」とすれば画面回転を制限
　できたので、電話がかかってきて破壊されたときぐらいしか役に立たない機能となった。
 
・前の問題へ戻った際に、先に表示されていたものと違う方の画像（1つの問題に2種類の画像がある）が
　表示されてしまうことがあるのを直した（randomNumListにどちらの画像を表示するかの乱数を格納して
  保存するようにした）。

・QuizActivityで再度タグを読み込みなおす動作が無駄だったため、SetQuizFragmentからQuizActivityへ
　画面遷移する際、Bundleにタグ等を入れて渡すように変更した。
 
・画面遷移の関数の後でfinish()を呼んでActivityを終了することで、バックキーを押した際
　戻ってほしくない画面に戻ることがないようにした。
 
・SetQuizFragmentのスピナーでNullPointerExceptionが出て前回の選択問題数が反映されない不具合を
　解消した（スピナーのインスタンスが生成される前に前回の設定を読み込む関数が呼ばれていたのが
  原因だった）。
 
・SetQuizFragmentにおいて該当件数が0件のときはクイズをスタートせず、トーストを表示するようにした。

・命名に明らかな誤りのあるもの等、一部の変数名の変更を行った。


変更点（レイアウト）
・QuizActivityのレイアウトにおいて、ImageViewと下のボタン群との位置をlayout_weightで
　余白の比率を調整することで決定するようにし、使用端末によっては画面下に大きな空白が
　生まれないようにした。
 
・res/drawableに「shape_rounded_corners.xml」を作成し、これをbackground属性で参照することで
　一部のボタンの角の丸みを柔らかくした。
 
・一部のレイアウトファイルの変更を行った。変更したのは位置関係のみであり、Viewの追加、削除は行っていない。


 
 
