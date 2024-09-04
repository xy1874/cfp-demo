# MkDocs入门指南

&emsp;&emsp;MkDocs是一个便捷易用的静态网页生成工具，详见<a href="https://www.mkdocs.org/" target="_blank">官网</a>。



## 1. 环境安装

&emsp;&emsp;此处仅介绍Windows 10系统下如何搭建MkDocs开发环境。其他系统下的环境搭建过程类似，此处不赘述。

### 1.1 Python环境安装

&emsp;&emsp;首先，从<a href="https://www.python.org/downloads/windows/" target="_blank">Python官网</a>下载适用于Windows的最新的Python3环境安装包，如图1-1所示。

<center><img src="../assets/1-1.png"></center>
<center>图1-1 从Python官网下载最新的Python环境安装包</center>

&emsp;&emsp;双击所下载的`python-3.XX.X-amd64.exe`安装包，勾选`Add Python 3.XX to PATH`，并点击`Install Now`，如图1-2所示。

<center><img src="../assets/1-2.png" width = 600></center>
<center>图1-2 为Windows 10安装Python环境</center>

### 1.2 依赖包安装

&emsp;&emsp;安装完毕后，在Windows 10搜索栏输入`powershell`，并在其上右键，选择`以管理员权限运行`，如图1-3所示。

<center><img src="../assets/1-3.png" width = 400></center>
<center>图1-3 以管理员权限打开PowerShell</center>

&emsp;&emsp;在PowerShell中输入`pip install mkdocs`命令并回车，以安装mkdocs。类似地，使用同样的命令依次安装`mkdocs-material`、`mkdocs-material-extensions`、`mkdocs-minify-plugin`、`pymdown-extensions`与`python-markdown-math`。

!!! info "PS :bulb:"
    &emsp;&emsp;也可以从本仓库的stupkt目录下载<a href="https://gitee.com/hitsz-cslab/gitee-page-demo/blob/master/stupkt/requirements.txt" target="_blank">requirements.txt文件</a>，然后在PowerShell中执行`pip install -r <file-path>/requirements.txt`命令安装依赖包。

&emsp;&emsp;至此，环境搭建完毕。



## 2. MkDocs开发

### 2.1 创建MkDocs工程
&emsp;&emsp;如果希望从零开始创建MkDocs工程，则可以在指定的路径下执行`mkdocs new <proj-name>`命令以创建新的MkDocs工程。

&emsp;&emsp;如果对MkDocs不熟悉，也可以在模板工程或现有工程的基础上进行修改和定制。

### 2.2 MkDocs工程配置

&emsp;&emsp;一个MkDocs工程通常包括`docs文件夹`、`site文件夹`、`mkdocs.yml配置文件`和`README.md`四部分。

- `docs文件夹`

&emsp;&emsp;该文件夹存放的是需要开发者编辑的由Markdown语言描述的静态文本。MkDocs工具将对该文件夹下的Markdown文本进行解析和转换，生成对应的HTML文本。

- `site文件夹`

&emsp;&emsp;该文件夹存放的是MkDocs生成的HTML网页。

- `mkdocs.yml`

&emsp;&emsp;该文件是MkDocs工程的配置文件。开发者通过修改该文件中的配置，不仅可以选择静态网页的主题、自定义网页配色，还可以将`docs文件夹`下的Markdown文本组织成指定的层次结构。

&emsp;&emsp;配置文件内各项配置的含义请参考<a href="https://gitee.com/hitsz-cslab/gitee-page-demo/blob/master/mkdocs.yml" target="_blank">本模板工程的配置文件</a>中的注释。

- `README.md`

&emsp;&emsp;该文档用于说明MkDocs工程的用途、使用声明等信息。该文件的内容将显示在GitHub或Gitee仓库的首页。

!!! info "PS :bulb:"
    &emsp;&emsp;`stupkt文件夹`可用于存放PDF、压缩包等材料。

### 2.3 Markdown编写

&emsp;&emsp;关于Markdown语法，请查阅<a href="https://markdown.com.cn/" target="_blank">官方文档</a>。

### 2.4 静态网页预览及调试

&emsp;&emsp;开发过程中，若想预览静态网页，可以在MkDocs工程的根目录上打开PowerShell，并执行`mkdocs serve`命令。然后打开浏览器，访问`http://localhost:8000/`即可预览静态网页。

!!! info "PS :bulb:"
    &emsp;&emsp;预览效果通常和最终部署的效果一致。另外，在调试过程中，可能出现因为网页缓存导致的预览效果与实际Markdown代码不一致的情况。此时，可打开网页的开发者工具，禁用缓存，然后刷新网页。

&emsp;&emsp;需要注意的是，预览时MkDocs工具生成的静态网页是临时的。因此，当文档撰写完毕，在正式部署前，必须在MkDocs工程的根目录上执行`mkdocs build`命令以生成HTML文本。此时，`docs文件夹`下的Markdown文件才与`site目录`下的HTML文件一一对应。



## 3. GiteePage部署

### 3.1 GitHub Desktop安装

&emsp;&emsp;如果熟悉Git工具，可通过相应的命令将本地的MkDocs工程提交到GitHub或Gitee平台，并进行后续的部署工作。否则，也可以先从GitHub官网上下载并安装<a href="https://desktop.github.com/" target="_blank">GitHub Desktop工具</a>。

### 3.2 创建并同步Gitee仓库

&emsp;&emsp;登录Gitee，加入<a href="https://gitee.com/hitsz-cslab" target="_blank">Gitee组织</a>后，于组织内新建Gitee空白仓库。

!!! info "PS :bulb:"
    &emsp;&emsp;视情况可创建开源仓库或私有仓库。若创建私有仓库，则无权限用户不可访问仓库本身，但仍可访问GiteePage静态网页。

&emsp;&emsp;然后，在GitHub Desktop工具中，点击`File`->`Clone repository`，并在`URL`处填入上述建立的Gitee仓库链接以及本地文件夹路径，如图1-4所示。

<center><img src="../assets/1-4.png" width = 500></center>
<center>图1-4 通过GitHub Desktop工具将Gitee仓库克隆到本地文件夹</center>

!!! info "PS :bulb:"
    &emsp;&emsp;克隆时，需要输入Gitee仓库创建者或仓库成员的账号密码。

&emsp;&emsp;打开所克隆仓库的本地文件夹，使用快捷键`Ctrl`+`A`选中所有文件并删除，并将MkDocs工程根目录下的所有文件拷贝进来。

&emsp;&emsp;接下来，回到GitHub Desktop工具。此时，该工具将自动显示当前仓库的变更内容。

&emsp;&emsp;在`Summary (required)`编辑框中输入本次更新内容的概要，点击`Commit to master`按钮，如图1-5所示。

<center><img src="../assets/1-5.png"></center>
<center>图1-5 提交仓库更新内容至master分支</center>

&emsp;&emsp;点击`Push origin`按钮，将更新上传到Gitee仓库，如图1-6所示。

<center><img src="../assets/1-6.png"></center>
<center>图1-6 上传仓库更新内容至Gitee</center>

### 3.3 开启GiteePage服务

&emsp;&emsp;上传完成后，在Gitee仓库页面即可看到已上传的MkDocs工程。此时，点击`服务`->`Gitee Pages`，如图1-7所示。

<center><img src="../assets/1-7.png"></center>
<center>图1-7 进入GiteePage服务</center>

&emsp;&emsp;进入GiteePage服务页面后，在部署目录处输入`site`，并勾选`强制使用HTTPS`，再点击启动按钮，如图1-8所示。

<center><img src="../assets/1-8.png" width = 550></center>
<center>图1-8 启动GiteePage服务</center>

&emsp;&emsp;启动成功后，可点击所显示的链接打开静态网页，如图1-9所示。

<center><img src="../assets/1-9.png" width = 600></center>
<center>图1-9 访问GiteePage静态网页</center>



## 4. Cloudflare部署

&emsp;&emsp;由于GiteePage服务目前已长时间处于暂停维护状态，此处更新基于Cloudflare的静态网页部署方法。Cloudflare的优点是不需经过VPN也能快速访问静态网页，且开发者只需要将构建好的静态网页更新到GitHub仓库，Cloudflare即可自动更新网页，而不需要开发者手动更新。

### 4.1 加入GitHub组织（选）

&emsp;&emsp;首先，向组织管理员提供用户名或注册邮箱以加入组织，如图1-10所示。

<center><img src="../assets/1-10.png" width = 500></center>
<center>图1-10 加入GitHub组织</center>

### 4.2 创建仓库

&emsp;&emsp;参考<a href="../mkdocs_guide/#2-mkdocs" target=_blank>第2节-MkDocs开发</a>在本地环境中构建好静态网页，在GitHub组织（或个人账户中）创建仓库，并参考<a href="../mkdocs_guide/#32-gitee" target=_blank>3.2节 创建并同步Gitee仓库</a>将本地仓库更新到对应的GitHub仓库。

### 4.3 连接Cloudflare与GitHub

&emsp;&emsp;打开链接<a href="https://pages.dev" target=_blank>pages.dev</a>，登录或注册你的Cloudflare账户。

&emsp;&emsp;点击左侧栏目中的“Workers & Pages”，点击右侧页面的“Pages”，然后点击“Connect to Git”按钮，如图1-11所示。

<center><img src="../assets/1-11.png" width = 100%></center>
<center>图1-11 进入Cloudflare的Pages功能</center>

&emsp;&emsp;点击右侧页面中的“Connect GitHub”按钮，如图1-12所示。

<center><img src="../assets/1-12.png" width = 100%></center>
<center>图1-12 点击连接GitHub账户</center>

&emsp;&emsp;随后Cloudflare将跳转到GitHub网页，并提示你需要将Cloudflare Pages服务安装到哪个账户，如图1-13所示。

<center><img src="../assets/1-13.png" width = 400></center>
<center>图1-13 选择GitHub账户以连接到Cloudflare</center>

&emsp;&emsp;在图1-13中，选择一个你需要连接的账户，随后根据个人需要设置是否对所有仓库开启Cloudflare Pages服务，并点击“Install & Authorize”按钮，如图1-14所示。

<center><img src="../assets/1-14.png" width = 400></center>
<center>图1-14 设置Cloudflare Pages服务的安装范围</center>

&emsp;&emsp;Cloudflare支持连接多个GitHub账户。如有需要，可自行添加。

### 4.4 创建Cloudflare Pages

&emsp;&emsp;在网页回到Cloudflare页面后，在右侧选择一个GitHub账户，然后选择该GitHub账户下的静态网页仓库，并点击“Begin Setup”按钮，如图1-15所示。

<center><img src="../assets/1-15.png" width = 650></center>
<center>图1-15 选择GitHub仓库以创建Cloudflare Pages项目</center>

&emsp;&emsp;然后，在“Project name”编辑框中输入Cloudflare Pages工程的名字。注意，**所生成的静态网页的默认网址是`<project-name>.pages.dev`**。<u>建议尽量起一个简洁好记的工程名</u>。

&emsp;&emsp;如果对应的GitHub仓库有多个分支，可在“Production branch”中选择一个分支来构建Cloudflare Page，如图1-16所示。

<center><img src="../assets/1-16.png" width = 500></center>
<center>图1-16 选择GitHub仓库的某个分支以构建静态网页</center>

&emsp;&emsp;随后在“Framework preset”中选择“MkDocs”，并点击“Save and Deploy”按钮即可，如图1-17所示。

!!! tip "小提示"
    &emsp;&emsp;本地的MkDocs工程在更新到GitHub仓库之前，最好先执行一次`mkdocs build`命令，否则Cloudflare构建静态网页可能失败。

<center><img src="../assets/1-17.png" width = 100%></center>
<center>图1-17 选择MkDocs预设并点击部署按钮</center>

&emsp;&emsp;首次构建需等待1~3分钟。构建完毕后，打开`<project-name>.pages.dev`，即可访问静态网页。

&emsp;&emsp;后续需要更新静态网页内容时，只需使用Git工具，将本地的更新内容同步到GitHub仓库即可。Cloudflare将自动检测GitHub仓库的更新动态并自动更新静态网页。Cloudflare基本可以实现在数秒内将静态网页的内容进行更新，如果等待片刻后，静态网页内容尚未更新，则可能是更新失败。

!!! warning "自动更新失败怎么办？"
    &emsp;&emsp;有些时候，GitHub仓库被更新后，Cloudflare自动更新网页会出现失败的情况。此时，只需登录Cloudflare账户，在图1-11所示的界面找到部署失败的Cloudflare Pages工程，如图1-18所示。

    <center><img src="../assets/1-18.png" width = 100%></center>
    <center>图1-18 登录Cloudflare，找到部署失败的工程</center>
    
    &emsp;&emsp;点击进入Cloudflare Pages工程页面，再点击“查看详细信息”，如图1-19所示。

    <center><img src="../assets/1-19.png" width = 100%></center>
    <center>图1-19 点击查看Cloudflare Page的部署详细信息</center>

    &emsp;&emsp;最后，点击“构建日志”下方的“重试部署”按钮即可，如图1-20所示。

    <center><img src="../assets/1-20.png" width = 100%></center>
    <center>图1-20 重试部署</center>

    &emsp;&emsp;一般重试部署后即可成功，若还是失败，则再次点击“重试部署”按钮。若多次重试仍然失败，则根据构建日志中的报错提示进行纠错，或尝试重新构建Cloudflare Pages工程。

### 4.5 多个部署的回滚或删除

&emsp;&emsp;每次更新GitHub仓库，或手动点击部署按钮，都会在Cloudflare Pages工程下生成一个对应的部署，如图1-21所示。

<center><img src="../assets/1-21.png" width = 100%></center>
<center>图1-21 Cloudflare Pages的多个部署</center>

&emsp;&emsp;一般地，访问`<project-name>.pages.dev`时，默认选中图1-21所示的最新的部署。开发者还可以参考图1-21所示的操作对这些部署进行回滚、重试或删除。
