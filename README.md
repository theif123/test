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
