# php自动生成api文档  
作者: [Dust](http://dust101.lofter.com)  
----
## 注释示例:
	要注意第三行要有api
```
    /**
     * 获取所有列表
     * api post api.php/index/index/lists
     * @param integer $page 页数
     * @param integer $limit 每页个数
     * @return array $void 结果
     */
    public function lists(){
    	.....
```   

```
    /**
     * 获取我的列表
     * api post api.php/index/index/my_list
     * @param integer $page 页数
     * @param integer $limit 每页个数
     * @return array 233
     */
    protected function lists(){
    	.....
```    

## 如何使用  
### 1.放置文件
	将 mumbaicat 放在 extend 目录下  

### 2.引入
	use mumbaicat\apidoc\ApiDoc;  

### 3.在合适地方放入代码
	$doc = new ApiDoc('../application'); // 参数1是代码目录,参数2是保存路径,参数2默认是当前路径.
	$doc->setName('api'); // 设置项目成功,不写此行默认是api,生成 项目名称.html 的文件,注意保存路径下是否有同名的文件,会被覆盖.
	$doc->make();  // 生成

### 4.查看文档
	项目名称.html ,默认是api.html  

## 将来版本:
 * 在线ajax  
 * ...