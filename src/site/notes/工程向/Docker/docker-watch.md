---
{"dg-publish":true,"permalink":"//docker/docker-watch/"}
---


作用：开发时根据文件变化自动编译/执行某个服务

docker compose watch 由一系列规则组成，每个规则必须包含  path 和 action

可用的 action：
- sync：自动将 host 上的文件修改同步到 docker 内。适用于能热更新的应用。
- rebuild：重新启动一个新的 image，等价于 `docker compose up --build <svc>`
- sync+restart：将 host 上的文件修改同步到 docker 内，并且重启容器。（e.g. 适用于 config 的修改）

target：控制 path 如何映射到容器内部
For `path: ./app/html` and a change to `./app/html/index.html`:
- `target: /app/html` -> `/app/html/index.html`
- `target: /app/static` -> `/app/static/index.html`
- `target: /assets` -> `/assets/index.html`