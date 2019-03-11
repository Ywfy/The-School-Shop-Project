# 校园商铺项目小点

## 1、创建maven项目后出现报错，The superclass "javax.servlet.http.HttpServlet" was not found on the Java Build Path
右键项目属性，进入Java Build Path --> Libraries --> Add Library --> Server Runtime --> Tomcat，finish完成

## 2、跟着老师敲的时候，在tb_area表单创建时出现问题
经试验，去掉字段名的单引号即可，如下
```
USE o2o;
CREATE TABLE tb_area(
	area_id int(2) NOT NULL auto_increment,
  area_name VARCHAR(200) NOT NULL,
  priority int(2) NOT NULL DEFAULT '0',
  create_time datetime DEFAULT NULL,
  last_edit_time datetime DEFAULT NULL,
  PRIMARY KEY (area_id),
  UNIQUE KEY UK_AREA(area_name)
) ENGINE=INNODB auto_increment=1 DEFAULT CHARSET=utf8;
```

# 3、若修改了web.xml,则必须保存后重启服务器才会生效
