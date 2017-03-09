#模板变量的说明
${basepackage} 代码存的包结构
${module} 模块名称
${Entity} 数据库表对应的实体名称,首字母大写
${entity} 数据库表对应的实体名称,首字母小写
	
#下面提供4个常用的模板
    - category模板，这个模板用来生成特定的表的，这个表的描述是XX分类表，例如一级分类，二级分类(DAO层用JDBC)
    - hibernate模板，表示DAO层是用hibernate
    - jdbc模板，表示DAO层是用spring jdbc的
    - pojo模板，只生成数据库表对应的实体类
    - 自定义模板的说明，可添加多个目录

#自定义模板，你可以在template文件下建立新的自定义模板,结构约定如下
    - src
    - WebRoot
    在这两件文件下，你可以自由的定义模板程序了
    	
    	
#修改记录
 
2015-10-28
ComponentUtil.java中getSysPath方法返回改为 System.getProperty("user.dir");原返回是取编译后的class文件所在目录
 
2015-11-1 
单表form加了验证;//form.jsp
 
2015-12-1
DBConstant.java 42行：
1.加了map.put("TIMESTAMP(6) WITH TIME ZONE", "java.util.Date");
39行：.加了map.put("TIMESTAMP(9)", "java.util.Date");
2.${Entity}Controller.java加了类注释：${table.comments} 
 
2015-12-03
${Entity}.java中27行加了：${field.comments_!""} 生成代码时{1:'',2:'',3:''}的注释

2016-01-12
1.TemplateUtil.getTemplateCategory()中27行对template作了非空验证
2.加了退出关闭窗口的监听器 AttachListener.java中

2016-04-26
1.TemplateUtil.java中140等处行加了时间map.put("data",...)

2016-10-11
1.controller类service的注入放到前面${Entity}Controller
2.${Entiry}实体类去除构造方法

2017-03-09
SurfaceCodeCtrl.java 43行 取当前系统的风格# CoderGenerate
