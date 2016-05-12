
# JS 组件化开发 系列
作为前端开发，组件化开发是你成长的必经之路。时间的积累逐渐摸索出自己比较好的开发方式。
# (1)实现最简单的组件化；
    var jdb ={
    alert: function(str) {
        alert(str);
    },
    console:function (str) {
        console.log(str)
    }
    }
     这样就是简单的实现 jdb.alert、jdb.console 两个方法。
    但是呢？
   现在需求改了，  需要实现链式调用. 就是像jquery一样使用。
  这也是很好理解的。怎么实现链式调用呢 。就像调用alert 或者console 这两个方法是jdb的属性和方法。
  要想调用， 需要 jdb.alert  。函数一旦执行完了就销毁了什么也没有了。要想在接着调用console 需要一个jdb对象。
  怎么产生呢？
  很简单！return this;   look !
  var jdb ={
    alert: function(str) {
        alert(str);
        return this;
    },
    console:function (str) {
        console.log(str)
    }
    };
    这样就实现了jdb.alert('先alert').console('后console');
    是不是很easy！
    接着问题又有了？
    如果要是现'先console'--'后alert'呢？
    也很简单,还是老方法   return this;  至于this 的用法自己补,这里不做赘述。或者有需要专门讲一下this。
 var jdb ={
    alert: function(str) {
        alert(str);
        return this;
    },
    console:function (str) {
        console.log(str);
        return this;
    }
    };
    这样就实现了简单的组件化开发，并实现了链式调用。

  组件就这么简单愉快的实现了。接下来是更高级的写法。。。。。敬请期待！



