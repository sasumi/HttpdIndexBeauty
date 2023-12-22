# Httpd Web Server 目录列表美化组件
## 安装使用
### Nginx类型站点配置方法
1. 打开指定站点conf文件，在配置文件中做如下配置
```editorconfig
server {
    # 其他 nginx 站点配置
    # ...

    # 在指定配置路径下开始启用
    location / {
        autoindex on; # 开启目录检索服务
        autoindex_exact_size off; # 关闭准确的文件大小检测
        autoindex_localtime on; # 启用文件本地时间显示
        autoindex_format html; # 强制index文件类型为html
        charset utf-8,gbk; # 强制页面编码为 utf-8 和 gbk，增强文件名称编码兼容性

        # 重要！引入项目html包含文件，注意，该路径为相对站点 root 配置路径，并非磁盘上的路径（不支持）
        add_after_body /HttpdIndexBeauty/dist/include.html;

        # ...站点其他配置
    }
}
```