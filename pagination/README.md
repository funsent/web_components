# 一款纯Javascript实现的前端分页插件

### 开发背景

随着前后端分离模式的逐渐流行，我们在项目中也经常通过局部刷新方式（ajax、fetch）请求远程数据，带来的好处显而易见。但是，前后端分离后原本应用的很多逻辑也带到了前端，导致前端复杂化，故也出现了Vue、React等类似于MVVM的一大堆前端框架，前端工程化开始在最近几年已经成为趋势，且已非常成熟。

只是受限于很多因素的原因，比如来自客户的、来自老板的、来自项目本身的、来自技术的等多层因素的影响，有时候我们不能不需要重复造轮子。比如上次开发的etable（一款基于jQuery的轻量级表格编辑插件，gitee地址：[etable插件](https://gitee.com/funsent/etable)），就是为了解决在现有项目中做到快速键盘操作的录单需要。

这次，我们也因类似原因，开发了一个纯javascript实现的分页插件 - pagination，小巧轻量，且和数据交互本身无关，可以非常方便的集成到现有项目中，该pagination分页插件目前自带一种样式。

另外一层自行开发的原因，也是让我们开发人员渐渐回归javascript本身，避免现在一个不好的现象：***很多前端新人只会Vue和jQuery，不会js原生写代码***，这样下去个人技术能力无法有效提高，我也时常和他们交流，也担心有一天Vue如同jQuery一样，不再流行的时候，我们团队成员如何适应如何面对，与其不断的学新技术，还不如以不变应万变，把基础打牢，将javascript等原生写法掌握的滚瓜烂熟，才不至于被各种新框架新技术牵着鼻子走，当然也就不会那么累了。

这里还要说一下后端开发，其实后端的技术栈也一样道理，我们很多后端开发人员，java的只会springboot、php的只会thinkphp、python的只会django，原生一点都不会写，甚至于这些框架根本就没有仔细研读过其实现原理，这样下去35岁年龄危机永远避免不了，内卷永远是内卷，技术缺失危机也永远存在。

废话说了那么多，接下去具体介绍下pagination分页插件：

### 插件演示

![插件样式](tests/demo.png)

### 插件使用

1. 建立页面结构

```html
<div class="pagination"></div>
```

2. 下载和引入pagination插件

```shell
# git clone https://gitee.com/funsent/pagination
```

```html
<script src="pagination.js"></script>
```

> pagination分页插件是纯javascript实现，不需要依赖其他任何组件

3. 初始化

```javascript
funsent.pagination.init('.pagination', {
    page: 1, // 当前页码
    pagesize: 10, // 每页显示记录数
    total: 0, // 总记录数
    goto: true, // 是否显示跳转框
    info: true, // 是否显示总页数总记录数
    disabled: true, // 相关分页链接是否标记禁用状态
    hide_single_page: false, // 总页数只有1页时是否隐藏分页条
    first_btn_text: '', // 第一页按钮文字
    prev_btn_text: '', // 上一页按钮文字
    next_btn_text: '', // 下一页按钮文字
    last_btn_text: '', // 最后页按钮文字
    change: function (pageIndex) {
        // change方法是点击分页链接时触发的方法，自己的业务逻辑可写在此处
        // pageIndex 参数为当前页码
    }
});
```

### 插件特点

- 纯javascript实现，不依赖第三方库
- 支持change方法实现自己的业务逻辑
- 内置一个简洁通用的分页样式
- 支持第一页、上一页等文字配置
- 支持单页时是否隐藏配置
- 支持启用按钮的禁用状态
- 支持配置是否显示跳转框和信息框
- 支持配置每页显示记录数和总记录数
- 支持一个页面多个pagination分页实例，互不干扰

### 意见建议

联系方式 QQ: 2018708，微信：younggf

> 加好友时请备注：etable插件