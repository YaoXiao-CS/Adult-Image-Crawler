这个video_scraper是名称为Adult-image-crawler项目的附属子项目。主要用于实现对目标网站的视频爬取测试，并用作目标检测的视频推理。

# 第一部分

首先是源码分析，找到视频地址。

```html
<dd><a href="/html/202506/111441.html" target="_blank" pcked="1"><h3><script type="text/javascript">document.write(d('5rCU6LSo5bCk54mp5aWz56We576O5bCR5aWz77yM5aSW6KGo5riF57qv55Sc576O77yM6Ieq5o+J5aSa5q+b5bCP6aqa6YC877yM5aSn5bGM54Ku5Y+L5rex5ZaJ77yM56yR5Zi75Zi777yM5oC85YWl6aqa56m05LiA6aG/5pON'));</script>气质尤物女神美少女，外表清纯甜美，自揉多毛小骚逼，大屌炮友深喉，笑嘻嘻，怼入骚穴一顿操</h3>
</a></dd>
```

这里的 `a href="/html/202506/111441.html" `真正的视频地址，而是一个跳转页面，点击后跳转得到视频播放页面，地址为：https://c4afcd.com/html/202506/111322.html

进一步分析源代码，发现视频真实地址存在于如下代码中：

```html
<div class="download">
<input style="outline-style: none ;border: 1px solid #ccc; border-radius: 3px;padding: 10px;    width: 30%;max-width: 700px;font-size: 14px;" type="text" size="30" id="url" value="https://d1.xia12345.com/video/202503/67dda0bdba8bde5fd5418e09/hd.mp4">
<a href="https://d1.xia12345.com/video/202503/67dda0bdba8bde5fd5418e09/hd.mp4" target="_blank" pcked="1"><script type="text/javascript">document.write(d('SFRUUOS4i+i9vQ=='));</script>HTTP下载</a>

<script type="text/javascript">
function copyUrl(){
 var url = document.getElementById("url").value;
 window.clipboardData.setData("Text",url);
 alert("复制链接成功！");
}
</script>
<input style="width: 55px;background-color: #333;font-size: 14px;color: #fff;margin: 10px 0px;padding: 10px;border-radius: 7px; " }type="button" value="复制链接" onclick="url.select();document.execCommand('Copy')">
</div>
```


# 第二部分

一个实现效果

| 名称              | 地址                                                                                                    | 备注                     |
| ----------------- | ------------------------------------------------------------------------------------------------------- | ------------------------ |
| downloaded_videos | [Google Drive Link](https://drive.google.com/file/d/1YD5Ni0RUaaaHLCdGFk3-VdB52_aXd-sR/view?usp=drive_link) | 存储到本地的成人视频数据 |
