# RESTful 框架
http://novoland.github.io/%E8%AE%BE%E8%AE%A1/2015/08/17/Restful%20API%20%E7%9A%84%E8%AE%BE%E8%AE%A1%E8%A7%84%E8%8C%83.html#vfhhe
## RestFul api定义
(1)Url只能有名词

 之前在项目中定义Api，犯了一个很严重的问题。没有遵守RestFul规范，Api资源路径中还有大量的动词。

在RESTful架构中，每个url代表一种资源（resource），所以Url不能有动词，只能有名词。

(2)单数名词表示单个资源，复数名词表示所有资源。

例如：获取产品的API可以这样定义

获取单个产品：http://127.0.01:8080/AppName/rest/product/1

获取多个产品:  http://127.0.01:8080/AppName/rest/products

(3)使用子资源表达关系

如果一个资源与另外一个资源有关系，使用子资源：

/product/1/images/ 返回id=1的产品的所有图片

/product/1/image/1 返回id=1的产品的其中一个图片

(4)URL参数

情况1：http://127.0.01:8080/AppName/rest/product/1

URL最后的1就是参数，表示获取id=1的产品，则在api定义的时候1作为PathParam

@GET

@Path("/{productId}")

@Produces("application/json;charset=utf-8")
public Response editUser(@PathParam("productId") longproductId)

情况2：资源上传

前台部分：@FormDataParam表单参数
情况3：post提交对象参数，添加或者编辑对象
(5)选择Http方法

常用的HTTP动词有下面四个（括号里是对应的SQL命令）。
GET（SELECT）：从服务器取出资源（一项或多项）。
POST（CREATE）：在服务器新建一个资源。
PUT（UPDATE）：在服务器更新资源（客户端提供改变后的完整资源）。
DELETE（DELETE）：从服务器删除资源。

之前在项目中定义的Api，在选择Http方法上，也存在不足。例如用Post也实现更新资源或者删除资源。虽然在功能实现上没有什么问题，但是不够规范，Api定义显得杂乱。