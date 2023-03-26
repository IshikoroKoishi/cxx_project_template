# C/C++プロジェクト向けディレクトリ構造テンプレート
/---
    |- (apps/)---  # Optional: 実行可能形式としての体裁を整えるためのコードを記述する．ここに含まれるコードは，OS，ユーザなどとインタラクションを行い，完全には制御できないような副作用を持つ．
                |- xxxx.cpp
    |- libs/---  # ロジックコードを記述する．ここに含まれるコードは副作用を持たないか，あるいは自己完結している．
                |- inc/---  # apps側へのインターフェース記述
                            |- xxxx.hpp
                |- src/---  # ロジックコード本体記述
                            |- xxxx.hpp
                            |- xxxx.cpp
            
    |- tests/---  # libsのテストコードを記述する．
                |- xxxx.cpp
    |- (scripts/)---  # Optional: 開発作業に必要なカスタムスクリプトを配置する．
    |- (ci/)---  # Optional: CI/CD関連のファイルを配置する．
                |- <tmp/>---  # AutoGen: CIの自動テスト，自動ベンチマークの結果の出力先．
    |- (packages/)---  # Optional: 外部依存を配置する
    |- <build/>---  # AutoGen: ビルドツリーフォルダ．ビルドツールが生成することを意図する．
                |- [PLATFORM]---  # x86-windows/x64-linux/arm64-osxなど
                            |- [BUILD_CONFIG]---  # Debug/Releaseなど
    |- <docs/>---  # AutoGen: ドキュメントファイルフォルダ．doxygen等の生成先とすることを想定．
    |- <dist/>---  # AutoGen: パッケージ出力先フォルダ
