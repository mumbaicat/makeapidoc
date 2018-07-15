# php注释自动生成api文档   v1.7
作者: [Dust](http://dust101.lofter.com)  
----
```  
composer require mumbaicat/makeapidoc "1.7"
```  

## 注释示例:
	与普通注释互不影响，带有 @method 和 @url 的才会生成  
    注释中备注不要有空格，建议使用标点符号来断句。  
```
    /**
     * 获取所有列表
     * @url api.php/index/index/all
     * @method POST
     * @param integer $page 页数
     * @param integer $limit 每页个数
     * @return integer $code 状态码
     * @return string $msg 返回消息
     */
    public function all($page,$limit){
    	// 地址中有三个占位符写法
    	// {url}/api.php/index/{controller}/{action}
        // {url} 会自动替换成设置的域名 $doc->url = 'xxx'; 来设置。
    	// {action} 会自动换成对应的方法名
    	// {controller} 会自动换成文件名(大驼峰会转成匈牙利)。
    	// --------------------------------
    	// 默认是文件名和方法名都开启大驼峰转换
    	// 文件名是大写字母出现1次以及以上就转换
    	// 方法名是大写字母出现2次以及以上就转换
        // 可以通过下面方法去改变,参数1是文件名,参数2是方法名
	    // $doc->setChange(true,true);
	    // $doc->setTime(1,2);
    }

    /**
     * 获取我的列表
     * @url api.php/index/index/my_list
     * @method GET
     * @return json json {'code':200,'msg':'json示例'}
     */
    public function my_list($page,$limit){
    	.....
    }

    /**
     * 获取我的名称
     * @url api.php/index/index/get_my_name
     * @method GET
     * @return string 名称
     */
    public function get_my_name(){
    	.....
    }

    /**
     * 添加数据
     * @url api.php/index/index/insert
     * @method GET
     * @param string $name 姓名
     * @param string $age 年龄
     * @return inetger $code 状态码
     */
    public function insert(){
    	.....
    }
```    

## 如何使用  

### 1.放置文件
	如果你是Thinkphp5，则将 extend 目录里的 mumbaicat 放在 TP5 的 extend 目录下 。

### 2.引入
    use mumbaicat\makeapidoc\ApiDoc;

### 3.在合适地方实例化
	$doc = new ApiDoc('../application');
	// 参数1是代码目录，参数2是保存路径，参数2默认是当前路径。 注意斜杠,windows是/ ，Linux/Mac是\ ，建议使用PHP常常量 DIRECTORY_SEPARATOR
	echo $doc->make();  

## 将来版本:
 * 等待您的提议 
 * ...  

## 截图:
![代码](https://github.com/mumbaicat/makeapidoc/raw/master/screenshot/code.png)  
![效果](https://github.com/mumbaicat/makeapidoc/raw/master/screenshot/html.png)  
![f12](https://github.com/mumbaicat/makeapidoc/raw/master/screenshot/request.png)  
