# openid 开发笔记
### openid 目前核心由hydra+dex组成。
### hydra 启动脚本。
    export FORCE_ROOT_CLIENT_CREDENTIALS=demo:demo
    export CONSENT_URL=http://localhost:4445/consent
    export DATABASE_URL=postgres://cdn:cdn@localhost:5432/mydb?sslmode=disable
    export SYSTEM_SECRET=hydra_test_app_need_first_second_third_four
    hydra host --dangerous-force-http

### hydra-consent-app-go
    export PORT=4445
    go run main.go

### 如果hydra启动异常，可先初始化下postgresql
    hydra migrate sql postgres://cdn:cdn@localhost:5432/mydb?sslmode=disable

### 都启动后，有个scope选项，如果选openid,则返回ID Token;如果选了offline则返回RefreshToken.
### hydra build errors:
1. JSONWebToken ->JSonWebToken.
2. OAuth2.IntrospectToken add one parameter.can use _,ar,err
3. update segmentio/analytics.go to V3.0.       ---git checkout V3.0
