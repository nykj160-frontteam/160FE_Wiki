# eslint 和 stylelint 集成说明文档

集成了 `eslint` 和 `stylelint` 来规范 `js` 代码和 `css` 代码，针对千人千面项目之后所有的新功能需求，旧有的业务不受影响。

## eslint

相关文件：`.eslintrc.js`，`.eslintignore`

### eslint 使用

`npm run lint:js`

### eslint 添加例外

在 `eslintignore` 文件下添加指定的路径，例如： `src/page/account/**/*.*`

## stylelint

基础支持所有类型的样式文件 `less` `css` `scss` `postcss` 等等
支持 `.vue` `.js` `.md` 等非样式文件里的行内样式

相关文件： `stylelint.config.js`

校验规则详见相关文件，另外一个需要提到的点是，针对已经定义好的规则，`stylelint` 支持样式属性的重新排序

### stylelint 使用

`npm run lint:css` 校验业务样式代码
`npm run lint:assets` 校验公共基础样式代码

### stylelint 添加例外

在配置文件的 `ignoreFiles` 选项中添加指定的路径。例如： `src/page/account/**/*.*`