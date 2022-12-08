# 这是一篇将 nodejs 代码发布到 npm 上的过程记录
- 如果你的代码文件夹目录下没有`package.json` 文件夹，可以运行 `npm init` 来自动创建它
- 新建一个文件来编写你的代码，但是记得千万要有一个叫 `index.js`或者`index.ts`的文件（文件名很重要，后缀就这两种之一） 
- 先运行一下文件，看看是不是正常的 `node index.ts`
- 去这个地址注册一个账号 `https://www.npmjs.com/`
- 开始登录 `npm login`，输入账号密码之后，你注册的邮箱会收到一封邮件，将邮件中的验证码输入即可。
- 确定你是否登录（登录成功会显示你的用户名）`npm whoami`
- 发布到仓库 `npm publish`
- 强制取消发布`npm unpublish nodejs-publish-demo --force` (可以去掉`--force` 变成不强制)

### 私有地址发布方式
- 在`package.json`中加以下代码，记得`registry`要填私有地址，别瞎填
```
"publishConfig": {
    "registry": "http://localhost/repository/npm-hosted/"
 }
```
- 同样开始登录，发包流程
#### 注意（非常重要）：
- 千万记得，这时候你是在私服上，`npm install` 的时候要注意，会导致你下载不到公共环境上才有的包
- 通过 `npm config set registry`设置的地址要与`publishConfig`下设置的地址一致才能发布成功