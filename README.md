# development-considerations
ycc的开发注意事项


H5:
    1. 获取视频第一帧作为封面 如果视频是公司的OSS上的资源 可以使用 视频地址 + '?x-oss-process=video/snapshot,t_1,m_fast'
    2. IOS端视频播放自动全屏问题 可以使用添加video标签属性 webkit-playsinline以及playsinline以及（为了兼容ios8、9）使用iphone-inline-video库           （https://github.com/fregante/iphone-inline-video）
    
