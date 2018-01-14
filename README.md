# makeapidoc
php自动生成api文档
作者: [Dust](http://dust101.lofter.com)  
----
## 注释示例:
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
	$obj = new ApiDoc();  

### 4.查看文档

## 将来版本  
	* 在线AJAX
	* ....  

	