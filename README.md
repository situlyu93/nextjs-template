This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## 使い方
```
git clone https://github.com/ユーザー名/next-template.git <project_name>

OR

mkdir <project_name>
cd <project_name>
git clone https://github.com/ユーザー名/next-template.git . 

```
- `cd <project_name>`
- `docker compose build`
- `docker compose up -d`

### npm ライブラリ追加方法
- appコンテナが起動中
  - `docker compose exec app npm install @chakra-ui/react`

- appコンテナが起動していない
  - `docker compose run --rm app npm install @chakra-ui/react`

- 反映されていない場合、以下を実行
  - `docker compose down && docker compose up -d`

## PC負荷が重いとき
```
//compose.yaml
    environment:
      WATCHPACK_POLLING: "300" //変更反映の速さ。500などに変えてみる。
```

## nextjsのバージョンUP , downなど
```
docker compose exec app npm install next@14 react@18 react-dom@18
docker compose exec app npm install -D eslint-config-next@14
```