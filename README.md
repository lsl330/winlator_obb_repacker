# winlator_obb_repacker
winlator的数据包拆包打包脚本

# 使用说明
本脚本分为拆包工具和打包工具

# 拆包工具
将unpacker文件和winlator的obb数据包文件main.1.com.winlator.obb，放在同一目录。然后运行./unpacker运行拆包工具。  
或直接运行curl -o unpacker https://raw.githubusercontent.com/lsl330/winlator_obb_repacker/main/unpacker && chmod +x unpacker && ./unpacker   
拆包工具会自动创建winlator文件夹和container-pattern（注意：若已有同名字目录会先删除再创建）  
container-pattern文件夹实际是继续拆包了winlator/opt/container-pattern.tzst(为啥要拆包此文件后续会有说明）  

# 打包工具
将repacker文件放在winlator和container-pattern文件夹的同一级目录（若没有上述两文件夹，则先运行拆包文件）  
或直接运行curl -o repacker https://raw.githubusercontent.com/lsl330/winlator_obb_repacker/main/repacker && chmod +x repacker && ./repacker   
脚本内置三种解包模式  
1-2为急速打包模式，推荐制作者调试obb使用，obb大小偏大，但打包时间极快（10秒左右，同时，强烈不推荐发布时使用此参数）  
3-4为官方推荐的压缩参数，建议在手机使用termux打包时使用  
5-6为极限压缩参数，建议在电脑上打包obb时使用（在最终发布时，个人强烈建议使用此参数，能尽可能减少obb的体积）  
7为中文补丁，可以为原版obb添加中文支持。  
8可以更换指定wine版本，但由于winlator目前自身的问题，仅支持更换8.5以下的版本。8.6以上版本替换会报错  

# container-pattern文件说明
container-pattern文件实际上是单独打包的wine文件。  
因此，或者制作包含游戏自启的obb（如游戏启动的shortcut就放在这里面），则需要修改该文件  
（打包时选2、4、6进行打包，若无修改container-pattern文件，则使用1、3、5打包）  


