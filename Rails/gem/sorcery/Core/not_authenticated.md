# not_authenticated
`require_login`内で、このメソッドも実行される。 
デフォルトでは`redirect_to root_path`と定義されているが、カスタマイズしたい場合は、`application_controller`で上書きする。
```
    class ApplicationController < ActionController::Base
      protected

      def not_authenticated
          redirect_to login_url, alert: 'ログインしてください'
　　　　　　　　　　　　end
    end
```
