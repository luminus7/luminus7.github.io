---
title: "kthread_run() macro in linux"
excerpt: "kthread_run()에 관한 정리"

categories:
    - Linux_kernel
tags:
    - Linux_kernel
last_mod_at: 2021-01-08T08:08:00-05:00
---


[문c 블로그 kthread_create, kthreadd link](http://jake.dothome.co.kr/kthreadd/)

include/linux/kthread.h

```c
/**
 * kthread_run - create and wake a thread.
 * @threadfn: the function to run until signal_pending(current).
 * @data: data ptr for @threadfn.
 * @namefmt: printf-style name for the thread.
 *
 * Description: Convenient wrapper for kthread_create() followed by
 * wake_up_process().  Returns the kthread or ERR_PTR(-ENOMEM).
 */
#define kthread_run(threadfn, data, namefmt, ...)                         \
({                                                                        \
        struct task_struct *__k                                           \
                = kthread_create(threadfn, data, namefmt, ## __VA_ARGS__);\
        if (!IS_ERR(__k))                                                 \
                wake_up_process(__k);                                     \
        __k;                                                              \
})
```
kthread_run() : 커널 쓰레드를 생성하는 api, create이후 조사까지.
@threadfn: entry point  
@data: 상동  
@namefmt: ?  