# 前端Script笔记

## document的相关用法

1.定义一个按钮

```html
<button value="你好" id="hello">你好</button>
```

2.定义一个let a去接收id为hello   **一定是id为hello**

```html
<script>
    //一定是id与id之间的名字相对应
			let a=document.getElementById("hello");
			console.log(a.value);
</script>
```

3.一定要注意id与id相对应，不然会出现报错

