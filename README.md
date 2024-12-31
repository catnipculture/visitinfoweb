> #### 作者主页：[舒克日记](https://blog.csdn.net/cativen)
>
>  简介：Java领域优质创作者、Java项目、学习资料、技术互助
>
> <b><font color=red>文中获取源码</font></b>

# 项目介绍

使用旅游信息网站的分为管理员和用户两个角色的权限子模块。

管理员所能使用的功能主要有：个人中心、用户管理、旅游景点管理、交流论坛、系统管理、订单管理等。

用户前台可以实现首页、旅游景点、论坛信息、新闻资讯、我的、跳转到后台、购物车、客服等。

# 环境要求

1.运行环境：最好是java jdk1.8,我们在这个平台上运行的。其他版本理论上也可以。

2.IDE环境：IDEA,Eclipse,Myeclipse都可以。推荐IDEA;

3.tomcat环境：Tomcat7.x,8.X,9.x版本均可

4.硬件环境：windows7/8/10 4G内存以上；或者Mac OS;

5.是否Maven项目：是；查看源码目录中是否包含pom.xml;若包含，则为maven项目，否则为非maven.项目

6.数据库：MySql5.7/8.0等版本均可；

# 技术栈

运行环境：jdk8 + tomcat9 + mysql5.7 + windows10

服务端技术：Java、Spring、SpringMVC、Mybatis，SSM

# 使用说明

1.使用Navicati或者其它工具，在mysql中创建对应sq文件名称的数据库，并导入项目的sql文件；

2.使用IDEA/Eclipse/MyEclipse导入项目，修改配置，运行项目；

3.将项目中config-propertiesi配置文件中的数据库配置改为自己的配置，然后运行；

# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq

源码地址：[http://www.codegym.top](http://www.codegym.top/)

其它问题请关注公众号：**IT小舟**,关注后发送消息即可，都会给您回复的。若没有及时回复请耐心等待，通常当天会有回复

# 运行截图

## 功能模块截图

![img](https://img-blog.csdnimg.cn/img_convert/cc6d8812cb4fec6e370826e0f5d020d4.png)

### 页面

#### 前台

![ssm287旅游信息网站7](https://img-blog.csdnimg.cn/img_convert/4c6a294bccaa1c17339416653103b326.png)

![ssm287旅游信息网站8](https://img-blog.csdnimg.cn/img_convert/6e0471d8cc246026e90955f4d5da6015.png)

![ssm287旅游信息网站9](https://img-blog.csdnimg.cn/img_convert/ae2763761af841e982ed7b91ad950bd3.png)

![ssm287旅游信息网站10](https://img-blog.csdnimg.cn/img_convert/f638d3b16a02c10898ccb66a483593f5.png)

![ssm287旅游信息网站11](https://img-blog.csdnimg.cn/img_convert/2e72ce65886ec89aed196fcc5e2ad008.png)

![ssm287旅游信息网站12](https://img-blog.csdnimg.cn/img_convert/90c5ae1f076b16fc63818b619ea18729.png)

![ssm287旅游信息网站13](https://img-blog.csdnimg.cn/img_convert/c4ecab83941ad9b524be77cab0a33b3e.png)

![ssm287旅游信息网站14](https://img-blog.csdnimg.cn/img_convert/7172a371502283f50294276ca6005063.png)

#### 后台

![ssm287旅游信息网站0](https://img-blog.csdnimg.cn/img_convert/fe422b1a51c31605d2b58477d4bcdad3.png)

![ssm287旅游信息网站1](https://img-blog.csdnimg.cn/img_convert/f476b00f2cfa91070719678cbddedd27.png)

![ssm287旅游信息网站2](https://img-blog.csdnimg.cn/img_convert/88e4f0b3441a07f8b3c9dfa01976c5a8.png)

![ssm287旅游信息网站3](https://img-blog.csdnimg.cn/img_convert/7fe881c5fcf9f743b87ba182e6dc53a4.png)

![ssm287旅游信息网站4](https://img-blog.csdnimg.cn/img_convert/26f9413dff0f8886060996b0da8acdd8.png)

![ssm287旅游信息网站5](https://img-blog.csdnimg.cn/img_convert/8809721cf259881342d61c149f37118a.png)
### 代码

```
    public Boolean updateSortIndex(List<MenuParamsDTO> menuParamsDTOList) {
        if (menuParamsDTOList == null || menuParamsDTOList.size() == 0) {
            throw new BizException("菜单列表不能为空");
        }
        int res = 0;
        for (MenuParamsDTO menuParamsDTO : menuParamsDTOList) {
            MenuDO menuDO = menuMapper.selectById(menuParamsDTO.getId());
            menuDO.setWeigh(menuParamsDTO.getWeigh());
            res = menuMapper.updateById(menuDO);
        }
        return res > 0;
    }
```
