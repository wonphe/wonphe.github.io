---
layout: post
title: "JQuery Validate使用总结"
categories: JQuery
description: "JQuery Validate使用总结"
keywords: JQuery
date: 2018-07-31 13:28:00
---

JQuery Validate使用总结：

## 1. 导入js库
```html
<script src="../js/jquery.js" type="text/javascript"></script>
<script src="../js/jquery.validate.js" type="text/javascript"></script>
```
## 2. 默认校验规则
| 规则 | 备注 |
| --- | --- |
| required:true | 必输字段 |
| remote:"check.php" | 使用ajax方法调用check.php验证输入值 |
| email:true | 必须输入正确格式的电子邮件 |
| url:true | 必须输入正确格式的网址 |
| date:true | 必须输入正确格式的日期 日期校验ie6出错，慎用 |
| dateISO:true | 必须输入正确格式的日期(ISO)，例如：2009-06-23，1998/01/22 只验证格式，不验证有效性 |
| number:true | 必须输入合法的数字(负数，小数) |
| digits:true | 必须输入整数 |
| creditcard: | 必须输入合法的信用卡号 |
| equalTo:"#field" | 输入值必须和#field相同 |
| accept: | 输入拥有合法后缀名的字符串（上传文件的后缀） |
| maxlength:5 | 输入长度最多是5的字符串(汉字算一个字符) |
| minlength:10 | 输入长度最小是10的字符串(汉字算一个字符) |
| rangelength:[5,10] | 输入长度必须介于 5 和 10 之间的字符串")(汉字算一个字符) |
| range:[5,10] | 输入值必须介于 5 和 10 之间 |
| max:5 | 输入值不能大于5 |
| min:10 | 输入值不能小于10 |

## 3. 默认的提示
```javascript
messages: {
    required: "This field is required.",
    remote: "Please fix this field.",
    email: "Please enter a valid email address.",
    url: "Please enter a valid URL.",
    date: "Please enter a valid date.",
    dateISO: "Please enter a valid date (ISO).",
    dateDE: "Bitte geben Sie ein g眉ltiges Datum ein.",
    number: "Please enter a valid number.",
    numberDE: "Bitte geben Sie eine Nummer ein.",
    digits: "Please enter only digits",
    creditcard: "Please enter a valid credit card number.",
    equalTo: "Please enter the same value again.",
    accept: "Please enter a value with a valid extension.",
    maxlength: $.validator.format("Please enter no more than {0} characters."),
    minlength: $.validator.format("Please enter at least {0} characters."),
    rangelength: $.validator.format("Please enter a value between {0} and {1} characters long."),
    range: $.validator.format("Please enter a value between {0} and {1}."),
    max: $.validator.format("Please enter a value less than or equal to {0}."),
    min: $.validator.format("Please enter a value greater than or equal to {0}.")
},
```
如需要修改，可在js代码中加入：
```javascript
jQuery.extend(jQuery.validator.messages, {
        required: "必选字段",
  remote: "请修正该字段",
  email: "请输入正确格式的电子邮件",
  url: "请输入合法的网址",
  date: "请输入合法的日期",
  dateISO: "请输入合法的日期 (ISO).",
  number: "请输入合法的数字",
  digits: "只能输入整数",
  creditcard: "请输入合法的信用卡号",
  equalTo: "请再次输入相同的值",
  accept: "请输入拥有合法后缀名的字符串",
  maxlength: jQuery.validator.format("请输入一个 长度最多是 {0} 的字符串"),
  minlength: jQuery.validator.format("请输入一个 长度最少是 {0} 的字符串"),
  rangelength: jQuery.validator.format("请输入 一个长度介于 {0} 和 {1} 之间的字符串"),
  range: jQuery.validator.format("请输入一个介于 {0} 和 {1} 之间的值"),
  max: jQuery.validator.format("请输入一个最大为{0} 的值"),
  min: jQuery.validator.format("请输入一个最小为{0} 的值")
});
```
推荐做法，将此文件放入messages_cn.js中，在页面中引入
```html
<script src="../js/messages_cn.js" type="text/javascript"></script>
```
## 4. 使用方式
### 1. 将校验规则写到控件中
```html
<script src="../js/jquery.js" type="text/javascript"></script>
<script src="../js/jquery.validate.js" type="text/javascript"></script>
<script src="./js/jquery.metadata.js" type="text/javascript"></script>
$().ready(function() {
 $("#signupForm").validate();
});

<form id="signupForm" method="get" action="">
    <p>
        <label for="firstname">Firstname</label>
        <input id="firstname" name="firstname" class="required" />
    </p>
 <p>
  <label for="email">E-Mail</label>
  <input id="email" name="email" class="required email" />
 </p>
 <p>
  <label for="password">Password</label>
  <input id="password" name="password" type="password" class="{required:true,minlength:5}" />
 </p>
 <p>
  <label for="confirm_password">确认密码</label>
  <input id="confirm_password" name="confirm_password" type="password" class="{required:true,minlength:5,equalTo:'#password'}" />
 </p>
    <p>
        <input class="submit" type="submit" value="Submit"/>
    </p>
</form>
```
使用class="{}"的方式，必须引入包：`jquery.metadata.js`

可以使用如下的方法，修改提示内容：
```javascript
class="{required:true,minlength:5,messages:{required:'请输入内容'}}"
```
在使用equalTo关键字时，后面的内容必须加上引号，如下代码：
```javascript
class="{required:true,minlength:5,equalTo:'#password'}"
```

### 2. 将校验规则写到js代码中

```javascript
$().ready(function() {
 $("#signupForm").validate({
        rules: {
   firstname: "required",
   email: {
    required: true,
    email: true
   },
   password: {
    required: true,
    minlength: 5
   },
   confirm_password: {
    required: true,
    minlength: 5,
    equalTo: "#password"
   }
  },
        messages: {
   firstname: "请输入姓名",
   email: {
    required: "请输入Email地址",
    email: "请输入正确的email地址"
   },
   password: {
    required: "请输入密码",
    minlength: jQuery.format("密码不能小于{0}个字 符")
   },
   confirm_password: {
    required: "请输入确认密码",
    minlength: "确认密码不能小于5个字符",
    equalTo: "两次输入密码不一致不一致"
   }
  }
    });
});
//messages处，如果某个控件没有message，将调用默认的信息
```
```html
<form id="signupForm" method="get" action="">
    <p>
        <label for="firstname">Firstname</label>
        <input id="firstname" name="firstname" />
    </p>
 <p>
  <label for="email">E-Mail</label>
  <input id="email" name="email" />
 </p>
 <p>
  <label for="password">Password</label>
  <input id="password" name="password" type="password" />
 </p>
 <p>
  <label for="confirm_password">确认密码</label>
  <input id="confirm_password" name="confirm_password" type="password" />
 </p>
    <p>
        <input class="submit" type="submit" value="Submit"/>
    </p>
</form>
```
    required:true 必须有值
    required:"#aa:checked"表达式的值为真，则需要验证
    required:function(){}返回为真，表时需要验证
后边两种常用于，表单中需要同时填或不填的元素


## demo：
```javascript
$("#form1").validate({//JQ 前端校验
                    rules: {
                    ctl00$MainContent$txtWebName: {
                            required: true,
                            maxlength: 500
                    },
                    ctl00$MainContent$txtShortName: {
                            maxlength: 500,
                            required: false
                    },
                    ctl00$MainContent$txtKeyWords: {
                            required: false,
                            maxlength: 500
                    },
                    ctl00$MainContent$txtGoodsNo: {
                            required: false,
                            maxlength: 250
                    },
                    ctl00$MainContent$txtRemark: {
                            required: false,
                            maxlength: 500
                    },
                    ctl00$MainContent$txtPageTitle: {
                            required: true,
                            maxlength: 1000
                    },
                    ctl00$MainContent$txtMetaKey: {
                            required: false,
                            maxlength: 1000
                    },
                    ctl00$MainContent$txtShowUrl: {
                            required: false,
                            maxlength: 2000,
                            url: true
                    },
                    ctl00$MainContent$txtOtherData: {
                            required: false,
                            maxlength: 1000
                    },
                    ctl00$MainContent$txtEC :{ required: true, digits: true},
                    ctl00$MainContent$txtFullEP : {required: true, digits: true},
                    ctl00$MainContent$txtMarketPrice : {required: true, number:true},
                    ctl00$MainContent$txtCash : {required: true,number:true},
                    ctl00$MainContent$txtDurationDays:{required: false,number:true},
                    ctl00$MainContent$txtFullCash:{required: true,number:true}
                    },
                    messages: {
                    ctl00$MainContent$txtWebName: "*请输入商品名[限500字以内]",
                    ctl00$MainContent$txtShortName: "*限500字以内",
                    ctl00$MainContent$txtKeyWords: "*500字以内",
                    ctl00$MainContent$txtGoodsNo: "*250字以内",
                    ctl00$MainContent$txtRemark: "*500字以内",
                    ctl00$MainContent$txtPageTitle: "*请输入分类页面的标题",
                    ctl00$MainContent$txtMetaKey: "*1000字以内",
                    ctl00$MainContent$txtShowUrl: "*请输入正确的URL地址",
                    ctl00$MainContent$txtOtherData: "*1000字以内",
                    ctl00$MainContent$txtEC:"*只能输入整数",
                    ctl00$MainContent$txtFullEP:"*只能输入整数",
                    ctl00$MainContent$txtCash:"*请输入正确的现金数",
                    ctl00$MainContent$txtFullCash:"*请输入正确的现金数",
                    ctl00$MainContent$txtDurationDays:"必须输入数字",
                    ctl00$MainContent$txtMarketPrice:"*请输入正确的市场价格"
                    }
                }); //validate
```