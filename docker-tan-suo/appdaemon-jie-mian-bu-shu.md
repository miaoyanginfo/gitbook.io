---
description: 更s适合平板操作的HomeAssistant控制界面
---

# 🏔 Appdaemon界面部署

<pre><code><strong>docker run --name=appdaemon -d -p 5050:5050 \
</strong>  --restart=always \
  -e HA_URL="&#x3C;your HA_URL value>" \
  -e TOKEN="&#x3C;your TOKEN value>" \
  -e DASH_URL="http://$HOSTNAME:5050" \
  -v &#x3C;your_conf_folder>:/conf \
  acockburn/appdaemon:latest
</code></pre>

安装完成之后访问主机的IP地址加端口5050就可以进入appdaemon的界面了。
