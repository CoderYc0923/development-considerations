# development-considerations
ycc的开发注意事项


H5:
    1. 获取视频第一帧作为封面 如果视频是公司的OSS上的资源 可以使用 视频地址 + '?x-oss-process=video/snapshot,t_1,m_fast'
    2. IOS端视频播放自动全屏问题 可以使用添加video标签属性 webkit-playsinline以及playsinline以及（为了兼容ios8、9）使用iphone-inline-video库           （https://github.com/fregante/iphone-inline-video） tips: 如果是APP中内嵌H5， 需要客户端配合修改 H5在 source标签的src上添加?playsinline=1, 客户端并对应代码中修改（configuration.allowsInlineMediaPlayback = true）
    3. IOS端H5视频播放监听canplay事件 可以在durationchange事件中 进行video.load()，这样canplay事件就可以在视频播放点击前被监听了。
    4.IOS内嵌H5页面，返回出现半截白屏问题及解决方案（可能跟ios回弹效果，组件有关系）
        定义：允许web应用程序在历史导航上显式地设置默认滚动恢复行为
        参数值：
            1. auto 将恢复用户已滚动到的页面上的位置
            2. manual 未还原页上的位置。用户必须手动滚动到该位置
            // 通过路由守卫，判断设置manual
            router.beforeEach((to, from, next) => {
                if (history.scrollRestoration) {
                    history.scrollRestoration = 'manual'
                    }
                })

    
