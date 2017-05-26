
>[(1)nil / Nil / NULL / NSNull](http://nshipster.cn/nil/)
>* Mattt Thompson撰写、 Zihan Xu翻译、 发布于2013年1月7日

---

>*cocoapods管理Podfile代码段

>source 'https://github.com/CocoaPods/Specs.git'
>source 'https://github.com/Artsy/Specs.git'
>
>platform :ios, '8.0'
># 引用框架
>use_frameworks!
># ignore all warnings from all pods(注解)
>inhibit_all_warnings!
>
>target 'nixsweibo' do
>    pod 'SDWebImage'
>    pod 'AFNetworking'
>    pod 'FMDB'
>    pod 'Masonry'
>    pod 'MMPlaceHolder', :head
>    pod 'MJRefresh'
>    pod 'MJExtension'
>    #pod 'MJPhotoBrowser' 手动引入，cocoapods上未找到
>    #pod 'MBProgressHUD' 手动引入，用的是拓展的
>end
>
>#Xcode里配置：项目名->Target->Build Settings->Enable BitCode中设置为NO就可以了.
>post_install do |installer|
>    installer.pods_project.targets.each do |target|
>        target.build_configurations.each do |config|
>            config.build_settings['ENABLE_BITCODE'] = 'NO'
>        end
>    end
>end
`
---
