### 推送

##### iOS推送有苹果推送和极光推送。

> 苹果推送链接：

```
http://devsdk.raysns.com/sunwenli/rsdk-base-server/src/push/server_push/devsdk/iosapplepushtest/v1?alert=Thisisaaaaaamessage&badge=2&deviceToken=["<f31835c3%208b37619a%20dd860e78%20f125948e%204075bbdf%20d418d828%202d61f9d1%20d9bdcb65>","<d9ae8f1f%20120440ae%207cb9d0dc%2015ac66cb%20b4bf2ded%204fc4d1fc%204c55c677%2073a2153e>"]
```

> 极光推送插件链接：

```
http://devsdk.raysns.com/sunwenli/rsdk-base-server/src/push/server_push/devsdk/iosjpushtest/v1?alert=Thisisaaaaaamessage&badge=2&deviceToken=[%22%3Cf31835c3%208b37619a%20dd860e78%20f125948e%204075bbdf%20d418d828%202d61f9d1%20d9bdcb65%3E%22,%22%3Cd9ae8f1f%20120440ae%207cb9d0dc%2015ac66cb%20b4bf2ded%204fc4d1fc%204c55c677%2073a2153e%3E%22
```

> 链接地址说明：
>
> 
`http://devsdk.raysns.com/sunwenli/rsdk-base-server/src/push/server\_push/devsdk/iosapplepushtest/v1`,
这部分是插件地址。

>**alert=**`Thisisaaaaaamessage&`**badge=2**`&`**deviceToken=**`[\[%22%3Cf31835c3%208b37619a%20dd860e78%20f125948e%204075bbdf%20d418d828%202d61f9d1%20d9bdcb65%3E%22,%22%3Cd9ae8f1f%20120440ae%207cb9d0dc%2015ac66cb%20b4bf2ded%204fc4d1fc%204c55c677%2073a2153e%3E%22\]`,
**alert,badge,deviceToken**这部分参数名是测试用的，不是正式的。

**上面链接里的参数是测试使用的，正式的参数及格式以下表为准。**

##### 参数说明：

| 参数名 | 说明 |
| :---: | :---: |
| push\_alias | 通知别名 |
| push\_device | 必传。设备token,数组 |
| notification\_title | 通知标题 |
| notification\_body | 必传。通知消息体 |
| custom\_data | 透传参数，Json |

> 对于游戏来说，所要做的操作是在游戏启动的时候获取到设备的唯一标识
`deviceToken`,存到游戏服务器。
`iOS`设备的`deviceToken`可以在游戏`AppDelegate.mm`类的生命周期方法里获取

```
- (void)application:(UIApplication *)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData *)pToken{
NSLog(@"---Token--%@", pToken);
//游戏需要存下这个token.
//send token to gameserver
}
```


