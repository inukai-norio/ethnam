# 未定義のアクションが指定された場合に特定のアクションを実行する

## 未定義のアクションが指定された場合に特定のアクションを実行する

想定外、あるいは許可されていないアクションがリクエストされた場合\*1、通常はアクションが未定義としてエラーになります。しかしながら、未定義のアクションが指定された場合にも特定のアクションを実行したくなることもあるかと思います(エラー用アクションや、問答無用でトップページを表示、等)。

こういった場合には、Ethna_Controller::main()メソッドの第3引数($fallback_action_name)に、アクション未定義の場合に実行したいアクション名を指定することで処理を実現することができます。具体的には、

    Sample_Controller::main('Sample_Controller', array(
     'index',
     'login_*',
    ), 'undef');

のように記述します。この場合は、第2引数に指定したアクション以外が指定されると'undef'アクションが実行されます(undefアクションが定義されていない場合はエラーとなります)。


* * *
\*1 [エントリポイント毎に実行可能なアクションを制限する](app-limitentrypoint.md)参照  

