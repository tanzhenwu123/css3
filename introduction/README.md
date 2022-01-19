## $css3简介$
> `1. 兼容版本`
> `2. css3的历史兼容记录`

|  前缀  |  代表浏览器  |
|  :----:  |  :----:  |
|  `-webkit`  |  `chrome或者safari`  |
|  `-moz`  |  `firefox`  |
|  `-ms`  |  `IE`  |
|  `-o`  |  `opear`  |

> `这是之前的写法，由于不同的浏览器兼容css的时间不同，所以在识别css3属性的时候需要在属性前面添加每个浏览器能够识别的前缀名`
```
div{
    -webkit-border-radius:50%;
    -moz-border-radius:50%;
    -o-border-radius:50%;
    -ms-border-radius:50%;
}
```
> `在后来的更新发现，所有的厂商都实现了css3的兼容，再后来所有的厂商不再使用单独的鉴别方法而是都实施了两种鉴别方法`
```
<!-- 传统写法 -->
div{
    -webkit-border-radius:50%;
    -moz-border-radius:50%;
    -o-border-radius:50%;
    -ms-border-radius:50%;
}

<!-- 干净写法 -->
div{
    border-radius:50%;
}
```

> `css3` [参考手册网站](http://css.doyoe.com)

> `css3` [权威查询网站](http://www.caniuse.com)

> `预处理器 less/sass cssNext插件`
```
<!-- less/sass语法糖 -->

$font-color:arial;
$mysituation-color:#333

div{
    span{
        color:$font-color;
    }
    p{
        color:$mysituation-color;
        i:{
            ...
        }
    }
}

<!-- cssNext语法 -->
:root{
    --headline-color:#333;
}

@custom-selector" --headline h1,h2,h3,h4,h5,h6

:--headline {
    color:var(--headline-color);
}
```

> `后处理器 autoprefixer`
```
<!-- 编写时 -->

div{
    border-radius:50%;
}

<!-- 运行时,自动补齐规则 -->

div{
    border-radius:50%;
    -webkit-border-radius:50%;
    -moz-border-radius:50%;
    -o-border-radius:50%;
    -ms-border-radius:50%;
}
```

> `postCss 工具,js实现的抽象css语法树`