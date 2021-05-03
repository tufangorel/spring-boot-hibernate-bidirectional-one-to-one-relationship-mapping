## spring-boot-hibernate-bidirectional-one-to-one-relationship-mapping

1- Implement hibernate bidirectional one-to-one relational mapping <br/>
2- ER diagram :  <br/><br/>

![alt text](https://github.com/tufangorel/spring-boot-hibernate-unidirectional-one-to-one-relationship-mapping/blob/main/customer_shipping_address_er_diagram-unidirectional-one-to-one.png)
<br/>

3- Start Spring Boot application with a specific profile such as "-Dspring.profiles.active=dev" . <br/>
4- swagger-ui can be accessed from URL : http://localhost:8080/customer-info/swagger-ui/ <br/><br/>

![alt text](https://github.com/tufangorel/spring-boot-hibernate-bidirectional-one-to-one-relationship-mapping/blob/main/springfox-swagger-ui.png)
<br/>

### Tech Stack
Java 11 <br/>
H2 Database Engine <br/>
spring boot <br/>
spring data jpa <br/>
spring web <br/>
hibernate <br/>
logback <br/>
maven <br/>
junit <br/>
springfox-swagger-ui <br/>
datasource-proxy <br/>
<br/>


## API OPERATIONS
### Save customer sucessfully to database

Method : HTTP.POST <br/>
URL : http://localhost:8080/customer/save <br/>

Request : 
<pre>
curl --location --request POST 'localhost:8080/customer-info/customer/save' \
--header 'Content-Type: application/json' \
--data-raw '{
    "name": "name1",
    "age": 1,
    "shippingAddress": {
        "streetName": "software",
        "city": "ankara",
        "country": "TR"
    }
}'
</pre><br/>

Response : 

HTTP response code 200 <br/>
<pre>
{
    "id": 1,
    "name": "name1",
    "age": 1,
    "shippingAddress": {
        "id": 1,
        "streetName": "software",
        "city": "ankara",
        "country": "TR"
    }
}
</pre>

### Find customer by shipping address id

Method : HTTP.GET <br/>
URL : localhost:8080/customer-info/shippingaddress/findcustomer/1 <br/>

Request : 
<pre>
curl --location --request GET 'localhost:8080/customer-info/shippingaddress/findcustomer/1' \
--header 'Content-Type: application/json' \
--data-raw '{}'
</pre><br/>

Response : 

HTTP response code 200 <br/>
<pre>
{
    "id": 1,
    "name": "name1",
    "age": 1,
    "shippingAddress": {
        "id": 1,
        "streetName": "software",
        "city": "ankara",
        "country": "TR"
    }
}
</pre><br/>
