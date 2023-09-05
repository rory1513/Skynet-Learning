# 基本概况
## Skynet工作流程

![Alt text](image/Skynet%E5%9F%BA%E6%9C%AC%E6%B5%81%E7%A8%8B%E5%9B%BE.png)

```c
//一个工作线程主要工作流程	
	
while(true)
	{
	    
	    queue = get_one_queue(global_queue) //通过全局队列拿到一个私有队列
	    
	    
        ctx  = get_ctx( queue->handle ) //通过队列拿到一个服务
	    
	    
	    msg = get_one_message(queue) //从队列里面取出一个消息
	       
	    
	    ctx->callback(msg) //调用服务的回调函数 ,在这个回调函数里面再调用一个固定的 lua函数
	   
	    
	}
	

```
