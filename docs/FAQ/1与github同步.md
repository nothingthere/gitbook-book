# 将gitbook中的项目与github同步

<https://help.gitbook.com/github/can-i-host-on-github.html>

通过简单的设置，使gitbook的项目与github同步，github每次提交就会自动更新gitbook项目。

总共分3步：

-   设置github的权限（每次登陆都需设置）
-   连接在github上的项目地址（每次创建gitbook项目都需要设置）
-   设置钩子（webhook）（每次创建gitbook项目都需要设置）

* * *

1.  设置github的权限

    -   进入gitbook的设置页面

        ```text
        https://www.gitbook.com/[[UserName]]/settings
        ```

    -   找到"GitHub"的面板（往下拉倒数第三个）选择"with access to public repositories"。

    -   回到页面顶部，点击左侧"Save"按钮保存。

2.  连接github上的项目地址（前提是已经在github上创建了相应的项目）

    -   进入github对应项目的设置页面

        ```text
        https://www.gitbook.com/book/[[UserName]]/[[Book]]/settings/github
        ```

    -   在"GitHub Repository"面板中填入`UserName/repo`。UserName为github用户名；rep为需要同步到github上的项目。比如在github上也创建了一个名为"try-gitbook"的项目，我的用户名为"username"，这里就应该是`lusername/try-gitbook`。

    -   回到页面顶部，点击"Save"按钮保存即可。

3.  设置钩子（webhook）

    -   回到上一步的页面，有一个"Integration"面板，点击"Add webhook"。

    -   下次直接使用`git push origin master`就可同时更新gitbook上的相应项目。

* * *

## 综合上述内容和[安装和初始化](../0安装和初始化.md)，结合github构建一个gitbook的步骤如下：

1.  在github上创建项目，本地初始化git工具。（与创建普通github项目步骤相同）
2.  在gitbook上创建对应项目。
3.  重复上面的后两步（假设已经设置完第一步）。
4.  正常提交github项目即可。
