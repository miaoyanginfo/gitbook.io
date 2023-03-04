# 🕹 免费薅狗东豆豆

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

利用docker搭建青龙面板，轻轻松松薅狗东的免费豆豆真的好香。。

```
docker run -dit \
-v /mnt/mmcblk2p4/docker/qinglong/config:/ql/config \
-v /mnt/mmcblk2p4/docker/qinglong/log:/ql/log \
-v /mnt/mmcblk2p4/docker/qinglong/db:/ql/db \
-v /mnt/mmcblk2p4/docker/qinglong/scripts:/ql/scripts \
-v /mnt/mmcblk2p4/docker/qinglong/jbot:/ql/jbot \
-v /mnt/mmcblk2p4/docker/qinglong/repo:/ql/repo \
-p 5700:5700 \
-e ENABLE_HANGUP=true \
-e ENABLE_WEB_PANEL=true \
--name qinglong \
--hostname qinglong \
--net=host \
--restart always \
whyour/qinglong:latest
```

{% hint style="info" %}
注意将上面脚本里面的/mnt/mmcblk2p4/docker/qinglong/repo替换为你本地挂载的文件夹路径。
{% endhint %}

运行完成之后登录容器的IP地址加端口5700就可以访问到我们部署好的青龙面板了。

登录之后要做的就是拉取大神制作的运行脚本了。
