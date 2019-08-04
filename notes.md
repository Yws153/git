第一天：
    打开对应文件夹的命令行，运行 npm init -y 可以快速初始化packgae.json文件
    尽量不要用cnpm来装包，会有坑
    npm run test & npm run pretest  并行
    npm run test && npm run pretest  串行
    webpack集群编译 scripty (前端云化编程)
        npm install --save-dev scripty
        https://www.npmjs.com/package/scripty
        应该会报个错：
        Warning: scripty - ignoring script "/Users/yeweishan/Documents/reactHooksTS/scripts/client/dev.sh" because it was not executable. Run `chmod +x "/Users/yeweishan/Documents/reactHooksTS/scripts/client/dev.sh" if you want scripty to run it.
        executable adj. 可执行的
        解决：chmod -R +x scripts 大意是给执行权限
        https://blog.csdn.net/u012106306/article/details/80436911

    npm install webpack --save-dev
    npm install webpack-cli --save-dev

    typeScript 语法了解一下：接口注入、lc、装饰器，类型推断等等
