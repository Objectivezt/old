# WeApp Media Components

## Audio

> 音频组件

1. `poster` 默认控件上的音频封面的图片资源地址，如果 controls 属性值 则设置 poster 无效
2. `controls` 是否显示默认控件
3. `loop` 是否循环播放

## Video

> 视频组件

1. danmu-list 弹幕列表
2. direction 设置全屏时视频的方向，不指定则根据宽高比自动判断
3. show-progress 若不设置，宽度大于 240 时才会显示
4. show-fullscreen-btn 是否显示全屏按钮
5. show-play-btn 是否显示视频底部控制栏的播放按钮
6. show-center-play-btn 是否显示视频中间的播放按钮
7. enable-progress-gesture 是否开启控制进度的手势

## Camera

> 相机组件

`mode` 应用模式，只在初始化时有效，不能动态变更
`resolution` 分辨率，不支持动态修改
`device-position` 摄像头朝向
`flash` 闪光灯，值为 auto, on, off
`frame-size` 指定期望的相机帧数据尺寸

## Image

> 图片组件

1. `mode` 图片裁剪、缩放的模式
2. `webp` 默认不解析 webP 格式，只支持网络资源
3. `lazy-load` 图片懒加载，在即将进入一定范围（上下三屏）时才开始加载
4. `show-menu-by-longpress` 开启长按图片显示识别小程序码菜单

## live-player, live-pusher

> 实时播放组件 实时录制组件 支持

1. 社交 直播
2. 教育 在线视频课程
3. 医疗 互联网医院，公立医院
4. 金融 银行、信托、基金、证券/期货
5. 汽车 汽车预售服务
6. 政府主体帐号
7. 工具 视频客服
