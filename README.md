"# test" 
"# test" 
# 实现一个对数组和对象深拷贝的方法
function copy(obj){
    var type=Object.prototype.toString.call(obj);
    if(!(type == '[object Array]' || type == '[object Object]')){
        return 'Type Error!';
    }
    return JSON.parse(JSON.stringify(obj));
}
