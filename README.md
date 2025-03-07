# site-info-api

使用方法示例：

https://api.info.mengze2.cn/api/v1/?url=https://mengze2.cn/

如果需要配置到 Stellar 主题中，写法就是：

```yaml
# 内置服务，按需加载（页面内用到了就会加载，没有用到就不会加载）
data_services:
  # 外部 md 渲染
  mdrender:
    js: /js/services/mdrender.js
  # 数据填充类
  siteinfo:
    js: /js/services/siteinfo.js
    # 设置 api 可以自动提取网页标题、图标，服务部署方法：https://github.com/xaoxuu/site-info-api/
    # 接口测试通过后，把按钮的 href 部分替换成 {href} 之后填写到下方，例如：https://api.vlts.cc/site_info/v1?url={href}
    api: 
```

## 支持 Vercel 部署

1. fork 本仓库
2. 打开 vercel.com，部署该项目
3. 进入 Environment Variables 页面，设置 HOSTS 如下：

| Key | Value |
| :-- | :-- |
| HOSTS | `['', 'localhost', 'mengze2.cn']` |

> 把示例中的最后一个修改为自己网站的 host 部分。
> 前两个分别代表空 Referrer、本地预览，可以根据需要选择是否保留。
