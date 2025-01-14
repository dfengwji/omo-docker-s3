# Usage

```bash
~# mkdir -p /data/omo-s3/files/public/files
~# docker run --restart=always --name=omo-s3 -p 7070:7070 -p 7777:7777 -p 7080:7080 -v /data/omo-s3/files:/root/files -d xtechcloud/omo-s3
```

# 私有区域

7070端口可以访问私有区域的文件,此区域的文件需要用户授权访问

默认管理员账号和密码为admin

`创建用户时，将scope定位到/root/files/目录下,例如/root/files/user01`

# 公共区域

7777端口提供公共区域的访问


## 命令上传文件

上传的URI地址为/files


- 上传到根目录

```bash
$ curl -T myfile your-domain:7777/files/
```

- 上传到指定目录

```bash
$ curl -T myfile your-domain:7777/files/1/2/
```

`注意：上传到目录时需要以 / 结尾`

- 上传到指定目录并重命名

```bash
$ curl -T myfile your-domain:7777/files/1/2/myfile.txt
```

## 命令下载文件

下载的URI地址为/files

```bash
$ wget your-domain:7777/files/myfile
```

## 页面浏览公共区域文件

7080端口提供公共区域的页面浏览，默认账号和密码为 
guest  guest@OMO



