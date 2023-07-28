# Vue 3 + Vite

This template should help get you started developing with Vue 3 in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

# 流れ

### 0.Node.jsのinstall

※既に入っていればskip

#### 0-1 下記からinstall

https://nodejs.org/ja

#### 0-2 正常にinstallされたか確認

```
node -v
```

```
>v18.16.1
```

みたいに出ればok

### 1.vue(vite)

#### 1-1 viteのプロジェクト作成

```
npm init vite@latest <project-name>
```

#### 1-2 プロジェクトディレクトリへ移動

```
cd <project-name>
```

#### 1-3 各種必要なpackageをinstall

```
npm install
```

### 2.eslint

#### 2-1 localでeslintを使用可能にする

```
npm install -g eslint-cli
```

参考↓↓↓↓↓
https://qiita.com/mysticatea/items/6bd56ff691d3a1577321

#### 2-2 eslintのinstall、dev fileに記録

```
npm install --save-dev eslint eslint-plugin-vue
```

#### 2-3 eslintのversionを確認

```
eslint -v
```

```
>v8.45.0
```

みたいに出ればok  
※スクリプト禁止が出る場合は下記を実行後、再度version確認

```
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process
```

#### 2-4 eslint 設定file作成

```
New-Item -type file .eslintrc.cjs
```

#### 2-5 .eslintrc.cjsへ下記をコピペ

```
module.exports = {
  extends: [
  // add more generic rulesets here, such as:
  // 'eslint:recommended',
  'plugin:vue/vue3-recommended',
  // 'plugin:vue/recommended'
  // Use this if you are using Vue.js 2.x.
  ],
  rules: {
  // override/add rules settings here, such as:
  // 'vue/no-unused-vars': 'error'
  }
}
```

#### 2-6 eslint　コマンド確認

```
eslint <filename *.vue or *.js>
```

error または warning の情報が出ればok 何も出なくてもok

### 3.prettier

#### 3-1 prettierのinstall、dev fileに記録、eslintのcode訂正を無効化

```
npm install --save-dev prettier eslint-config-prettier
```

#### 3-2 prettier file設定

```
New-Item -type file .prettierrc.cjs
```

#### 3-3 .prettierrc.cjsへ下記をコピペ

```
module.exports = {
  semi: false,
  singleQuote: true,
  tabWidth: 2,
  useTabs: false,
  printWidth: 120,
  proseWrap: 'preserve',
  trailingComma: 'all',
  // あなたの素晴らしいルール
}
```

#### 3-4 vscodeのsetting.json (user) へ下記を追加

※既に追記済みならskip

```
// 保存する同時に自動整形
"editor.formatOnSave": true,
// Prettierを使うファイル種類
"[javascript]": {
  "editor.defaultFormatter": "esbenp.  prettier-vscode"
},
"[typescript]": {
  "editor.defaultFormatter": "esbenp.  prettier-vscode"
},
"[vue]": {
  "editor.defaultFormatter": "esbenp.  prettier-vscode"
},
```

#### 3-5 コード整形を試す

App.vueへ下記のような、不細工なコードをうち

```
<div>1
</div>
```

保存後、下記のように整形されればok

```
<div>1</div>
```

### 4.その他

#### 4-1 プラグイン

Vue Language Features  
Vue Peek  
Vetur  
ESlint  
Prettier - Code formatter

終了
