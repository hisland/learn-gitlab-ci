# executor

- shell executor 相当于在命令行环境执行程序
- docker executor 在 docker 容器里面执行程序

# cache

- cache 是 GitLab 15.0 才有的特性, 之前得用其它方法
- cache 在不同的 pipeline 和 job 之间共享
- cache 会在 job 执行前恢复, 执行完之后保存
- 不同的 job, 相同的 cache:key, 会使用相同的 cache

所以

- 一个 cache:key 指定之后, 相应的缓存会一直存在, 反复被 job 修改并保存
- 要使用不同的 cache, 就给一个不同的 key, 或者手工去删掉原来的缓存 zip 包

# artifacts

- 一个 job 产生的输出可以打包在浏览器里面去下载
- 打包的东西下个 job 会自动得到
