### 实现一个对数组和对象深拷贝的方法
```
    function copy(obj){
        var type=Object.prototype.toString.call(obj);
        if(!(type == '[object Array]' || type == '[object Object]')){
           return 'Type Error!';
       }
        return JSON.parse(JSON.stringify(obj));
    }
    
    function clone (obj) {
      let buf
      if (obj instanceof Array || (obj instanceof Object && typeof obj !== 'function')) {
        buf = obj instanceof Array ? [] : {}
        for (let key in obj) {
          if (obj.hasOwnProperty(key)) {
              buf[key] = clone(obj[key])
          }
        }
      } else {
        return obj
      }
      return buf
    }
```
### 用css绘制一个红色的爱心
```
    .heart {
      position: relative;
      width: 100px;
      height: 90px;
    }
    .heart:before,
    .heart:after {
      position: absolute;
      content: "";
      left: 50px;
      top: 0;
      width: 50px;
      height: 80px;
      background: red;
      border-radius: 50px 50px 0 0;
      transform: rotate(-45deg);
      transform-origin: 0 100%;
    }
    .heart:after {
      left: 0;
      transform: rotate(45deg);
      transform-origin: 100% 100%;
    }
```
