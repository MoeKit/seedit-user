# 演示文档

---

````javascript
seajs.use('index', function(user){
      console.log(user.isLogin());
      user.getUserInfo(function(data){
        console.log('success',data);
      },function(error){
        console.log('fail',error);
      });
      console.log(user.buildAvatar('1158977'));
      console.log(user.config.defaultAvatar);
      
      setTimeout(function(){
         // 第二次获取用户信息不发api请求
        user.getUserInfo(function(data){
            console.log('第二次 success',data);
        },function(error){
            console.log('第二次 fail',error);
        });
      },3000); 
});

// 第二次引用 

setTimeout(function(){
    seajs.use('index', function(user){
          setTimeout(function(){
             // 第三次获取用户信息不发api请求
            user.getUserInfo(function(data){
                console.log('第三次 success',data);
            },function(error){
                console.log('第三次 fail',error);
            });
          },3000); 
    });
},5000);
````
