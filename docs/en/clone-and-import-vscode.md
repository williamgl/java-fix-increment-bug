# 下载项目代码并导入VSCode

> 我们深知在国内进行开发遇到的各种网络问题，因此为所有的服务设置了国内镜像，保证你即使完全没有魔法也能拥有极速的开发体验。
>
> 如果你是初学者，最好一步步按此文档操作，祝你好运！挫折常有，但请不要轻易放弃，不要让我们的努力付诸东流。:-)
>
> 有任何问题，请访问[ByteLegend](https://bytelegend.com)首页右下角的`联系 & 关于`菜单获取我们的联系方式。

因为你已经通过了之前的`git version`挑战，`git`应该已经正确安装，所以在你的终端（如macOS上的`Terminal`, Windows上的`cmd`(命令提示符)/`PowerShell`/`git-bash`等）输入：

`git clone https://git.bytelegend.com/ByteLegendQuest/java-fix-increment-bug`

这会在本地创建一个名为`java-fix-increment-bug`的项目文件夹，你可以把它移动到你喜欢的任何地方去。

打开`VSCode`，将刚才 Clone 下来的项目拖入VSCode中。请确保已经安装了
[Extension Pack for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack)。如果你之前没有在VSCode中配置过JDK，则点击侧边栏中的齿轮，选择`Settings`，在页面中找到`Configuration: Runtimes`配置，点击`Edit in settings.json`。

![vscode-jdk-setting](../vscode-jdk-setting.png)

按照如下格式进行 JDK 的配置：

```json
"java.configuration.runtimes": [
  {
    "name": "JavaSE-17",  // JDK 名称
    "path": "~/.sdkman/candidates/java/17.0.2-tem", // JDK 路径
    "default": true // 是否为默认值
  }
]
```

![vscode-jdk-conf](../vscode-jdk-conf.png)

如果你没有魔法，项目的导入可能会很慢，这是因为默认的Maven中央仓库在中国大陆没有CDN节点。
在你了解Maven原理之前，**请勿**贸然按照网上教程胡乱修改本地的Maven配置。
我们在项目中内置了阿里云镜像，一键开启，只对该项目生效，没有毒副作用。

打开本项目中的`.vscode/settings.json`文件，将`maven.executable.options`这行前面的注释（`//`）去掉，
关闭VSCode重新打开项目即可。

![vscode-aliyun](./vscode-aliyun.png)