#### npx
npx运行安装在node目录下的包
```
npx prettier src/App.js
```

#### prettier
perttier负责调整代码风格，代码样式
```
prettier --write "src/**/*.{js,jsx,css,html,json}"
```
prettier负责格式化文件，--write会按照格式化后的样式重写文件

#### eslint
eslint负责代码规则检查

eslint和prettier冲突的规则，可以采用`eslint-config-prettier`关闭不需要的规则

```
yarn add -D eslint eslint-config-prettier eslint-plugin-prettier
```

.eslintrc.json文件：
```json
{
  "extends": [
    "eslint:recommended",
    "prettier",
    "prettier/react"
  ]
}
```
prettier和prettier/react是去掉eslint中样式的部分