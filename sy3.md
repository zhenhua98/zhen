# 实验三：数据交互与技术

## 摘要：

本次实验介绍了数据交互的基本原理，SQL的基本原理和MongoDB的基本原理。通过Python与MySQL的交互实践具体介绍了交互的技术与过程。

## 关键词：

SQL, Python, MongoDB, 数据交互


## 1. SQL基本原理和简介

结构化查询语言(Structured Query Language)简称SQL，是一种数据库查询和程序设计语言，用于存取数据以及查询、更新和管理关系数据库系统；同时也是数据库脚本文件的扩展名。  
SQL 是一门 ANSI 的标准计算机语言，用来访问和操作数据库系统。SQL 语句用于取回和更新数据库中的数据。SQL 可与数据库程序协同工作，比如 MS Access、DB2、Informix、MS SQL Server、Oracle、Sybase 以及其他数据库系统。  
不幸地是，存在着很多不同版本的 SQL 语言，但是为了与 ANSI 标准相兼容，它们必须以相似的方式共同地来支持一些主要的关键词（比如 SELECT、UPDATE、DELETE、INSERT、WHERE 等等）。  
结构化查询语言包含6个部分：  

一：数据查询语言（DQL:Data Query Language）：
其语句，也称为“数据检索语句”，用以从表中获得数据，确定数据怎样在应用程序给出。保留字SELECT是DQL（也是所有SQL）用得最多的动词，其他DQL常用的保留字有WHERE，ORDER BY，GROUP BY和HAVING。这些DQL保留字常与其他类型的SQL语句一起使用。

二：数据操作语言（DML：Data Manipulation Language）：
其语句包括动词INSERT，UPDATE和DELETE。它们分别用于添加，修改和删除表中的行。也称为动作查询语言。

三：事务处理语言（TPL）：
它的语句能确保被DML语句影响的表的所有行及时得以更新。TPL语句包括BEGIN TRANSACTION，COMMIT和ROLLBACK。

四：数据控制语言（DCL）：
它的语句通过GRANT或REVOKE获得许可，确定单个用户和用户组对数据库对象的访问。某些RDBMS可用GRANT或REVOKE控制对表单个列的访问。

五：数据定义语言（DDL）：
其语句包括动词CREATE和DROP。在数据库中创建新表或删除表（CREAT TABLE 或 DROP TABLE）；为表加入索引等。DDL包括许多与人数据库目录中获得数据有关的保留字。它也是动作查询的一部分。

六：指针控制语言（CCL）：
它的语句，像DECLARE CURSOR，FETCH INTO和UPDATE WHERE CURRENT用于对一个或多个表单独行的操作。

### SQL 数据操作语言 (DML)
SQL (结构化查询语言)是用于执行查询的语法。但是 SQL 语言也包含用于更新、插入和删除记录的语法。

这些查询和更新语句都来自 SQL 的 DML 部分：

SELECT - 从数据库表中获取数据
UPDATE - 更新数据库表中的数据
DELETE - 从数据库表中删除数据
INSERT INTO - 向数据库表中插入数据
### SQL 数据定义语言 (DDL)
SQL 的数据定义语言部分使我们有能力创建或删除表格。我们也可以定义索引（键），规定表之间的链接，以及施加表间的约束。
SQL 中最重要的 DDL 语句:

CREATE TABLE - 创建新表
ALTER TABLE - 变更（改变）数据库表
DROP TABLE - 删除表
CREATE INDEX - 创建索引（搜索键）
DROP INDEX - 删除索引

## 2. Python与MySQL交互原理与实践

![示意图](https://img-blog.csdnimg.cn/20200805213525810.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNDA3ODQx,size_16,color_FFFFFF,t_70)




## 3. MongoDB的基本原理与简介

### 一、MongoDB概述

1、mongoDB概述

MongoDB 是一个基于分布式文件存储的数据库。由C++语言编写

2、NoSQL概述

NoSQL，指的是非关系型的数据库。NoSQL 有时也称作Not Only SQL 的缩写，
是对不同于传统的关系型数据库的数据库管理系统的统称。NoSQL 用于超大规模数据的存储

3、关系数据库对比非关系数据库

|关系型数据库               |      NoSQL 数据库|
---------------------------|---------|
|高度组织化结构化数据        |          代表着不仅仅是SQL|
|结构化查询语言（SQL）        |          没有声明性查询语言|
|数据和关系都存储在单独的表中  |          没有预定义的模式|
|数据操作语言，数据定义语言    |         键-值对存储，列存储，文档存储，图形数据库|
|严格的一致性                 |          最终一致性，而非ACID 属性|
|基础事务                     |           非结构化和不可预知的数据|
|                            |                      CAP 定理|
 |                            |                 高性能，高可用性和可伸缩性|

4、NoSQL数据库分类

列存储：Hbase/Cassandra

文档存储：MongoDB/CounchDB

key-value存储：Redis/Memcache

图存储：Neo4j/FlockDB

对象存储：Db4o

XML数据库：BaseX

5、CAP原则  
CAP 定理（CAP theorem）, 又被称作布鲁尔定理（Brewer's theorem）, 它指出对于一个分布式计算系统来说，不可能同时满足以下三点:

一致性(Consistency) (所有节点在同一时间具有相同的数据)  
可用性(Availability) (保证每个请求不管成功或者失败都有响应)  
分区容错性(Partition tolerance) (系统中任意信息的丢失或失败不影响系统的继续运行)  

CAP 理论的核心是: 一个分布式系统不可能同时很好的满足一致性，可用性和分区容错性这三个需求，最多只能同时较好的满足两个   

根据CAP 原理将NoSQL 数据库分成了满足CA 原则、满足CP 原则和满足AP 原则三大类：  

CA - 单点集群，满足一致性，可用性的系统，通常在可扩展性上不太强大。  
CP - 满足一致性，分区容错性的系统，通常性能不是特别高。  
AP - 满足可用性，分区容错性的系统，通常可能对一致性要求低一些。  

### 二、MongoDB体系结构



|关系数据库| MongoDB	|解释对比|
|--------|--------|--------|
|Database	|Database	|数据库/数据库|
|Table|	Collection	|数据库表/集合|
|Row	|Document	|数据库记录行/文档|
|Column	|Field	|数据列/数据字段|
|Index	|Index	|索引/索引|
|Table |join	 	|表关联/MongoDB不支持|
|Primary key	|Object ID	|主键/MongoDB自动将_id设为主键|

### 三、MongoDB数据类型

BSON( Binary Serialized Document Format) 是一种二进制形式的存储格式，采用了类似于 C 语言结构体的名称、对表示方法，支持内嵌的文档对象和数组对象，具有轻量性、可遍历性、高效性的特点. 

### 四、MongoDB底层原理

MongoDB 的集群部署方案中有三类角色：实际数据存储结点、配置文件存储结点和路由接入结点。   

MongDB客户端访问过程：连接的客户端直接与路由结点相连，从配置结点上查询数据，根据查询结果到实际的存储结点上查询和存储数据。  

MongoDB 的部署方案：单机部署、复本集（主备）部署、分片部署、复本集与分片混合部署。  

MongoDB 的分片：分片（sharding）是将数据拆分，将其分散存到不同机器上的过程。MongoDB 支持自动分片，
可以使数据库架构对应用程序不可见。对于应用程序来说，好像始终在使用一个单机的 MongoDB 服务器一样，
另一方面，MongoDB 自动处理数据在分片上的分布，也更容易添加和删除分片。

### 五、MongoDB应用场景

1、网站实时数据量大

2、数据读写都很频繁

3、价值较低

## 4. Python与MongoDB交互的原理与简介




## 5. MySQL与MongoDB的对比

### 一、关系型数据库-MySQL

1、在不同的引擎上有不同的存储方式。  
2、查询语句是使用传统的sql语句，拥有较为成熟的体系，成熟度很高。  
3、开源数据库的份额在不断增加，mysql的份额也在持续增长。  
4、缺点就是在海量数据处理的时候效率会显著变慢。  

### 二、非关系型数据库-MongoDB

非关系型数据库(nosql ),属于文档型数据库。先解释一下文档的数据库，即可以存放xml、json、bson类型的数据。这些数据具备自述性，呈现分层的树状数据结构。数据结构由键值(key=>value)对组成。

1、存储方式：虚拟内存+持久化。  
2、查询语句：是独特的MongoDB的查询方式。  
3、适合场景：事件的记录，内容管理或者博客平台等等。 
4、架构特点：可以通过副本集，以及分片来实现高可用。  
5、数据处理：数据是存储在硬盘上的，只不过需要经常读取的数据会被加载到内存中，将数据存储在物理内存中，从而达到高速读写。  
6、成熟度与广泛度：新兴数据库，成熟度较低，Nosql数据库中最为接近关系型数据库，比较完善的DB之一，适用人群不断在增长。  

### 三、MongoDB优势与劣势

优势：  
1、在适量级的内存的MongoDB的性能是非常迅速的，它将热数据存储在物理内存中，使得热数据的读写变得十分快。  
2、MongoDB的高可用和集群架构拥有十分高的扩展性。  
3、在副本集中，当主库遇到问题，无法继续提供服务的时候，副本集将选举一个新的主库继续提供服务。  
4、MongoDB的Bson和JSon格式的数据十分适合文档格式的存储与查询。  
劣势：  
1、 不支持事务操作。MongoDB本身没有自带事务机制，若需要在MongoDB中实现事务机制，需通过一个额外的表，从逻辑上自行实现事务。  
2、 应用经验少，由于NoSQL兴起时间短，应用经验相比关系型数据库较少。  
3、MongoDB占用空间过大。  

### 四、对比



|数据库|	MongoDB|	MySQL|
|------|-----------|---------|
|数据库模型	|非关系型	|关系型|
|存储方式|	以类JSON的文档的格式存储	|不同引擎有不同的存储方式|
|查询语句	|MongoDB查询方式（类似JavaScript的函数）	|SQL语句|
|数据处理方式	|基于内存，将热数据存放在物理内存中，从而达到高速读写|	不同引擎有自己的特点|
|成熟度	|新兴数据库，成熟度较低|	成熟度高|
|广泛度	|NoSQL数据库中，比较完善且开源，使用人数在不断增长|	开源数据库，市场份额不断增长|
|事务性|	仅支持单文档事务操作，弱一致性|	支持事务操作|
|占用空间	|占用空间大	|占用空间小|
|join操作	|MongoDB没有join	|MySQL支持join|


## 6. 关系数据与MySQL交互实验结果



```python
import mysql.connector
from mysql.connector import Error
import numpy as np
import pandas as pd
from functools import reduce
# 用户信息
host_name = "localhost"
user_name = "root"
user_password = "777" 
database_name = "book_shelf" 

# 函数: 连接数据库
def database_connection(host_name, user_name, user_password, db_name):
    connection = None
    try:
        connection = mysql.connector.connect(
            host=host_name,
            user=user_name,
            passwd=user_password,
            database=db_name
        )
        print("MySQL Database connection successful")
    except Error as err:
        print(f"Error: '{err}'")

    return connection
# 函数：执行查询或命令
def execute_query(connection, query):
    cursor = connection.cursor()
    try:
        cursor.execute(query)
        print('Query successful!')
    except Error as err:
        print(f"Error: '{err}'")

# 函数：导入数据
def  import_data(connection, create_table, insert_values, file_path):
    cursor = connection.cursor()
    try:
        cursor.execute(create_table)
        df = pd.read_csv(file_path)
        df = df.astype(object).where(pd.notnull(df), None)
        for i,row in df.iterrows():
            cursor.execute(insert_values, tuple(row))
        print("Import successful!")
        connection.commit()
    except Error as err:
        print(f"Error: '{err}'")    

```


```python
# 创建book_test数据库
def server_connection(host_name, user_name, user_password):
    connection = None
    try:
        connection = mysql.connector.connect(
            host=host_name,
            user=user_name,
            passwd=user_password
        )
        print("MySQL connection successful")
    except Error as err:
        print(f"Error: '{err}'")

    return connection
def create_database(connection, query):
    cursor = connection.cursor()
    try:
        cursor.execute(query)
        print("Database created successfully")
    except Error as err:
        print(f"Error: '{err}'")
connection_server = server_connection(host_name, user_name, user_password)
create_database_query = 'CREATE DATABASE ' + database_name
create_database(connection_server, create_database_query)

```

    MySQL connection successful
    Database created successfully
    


```python
# 建立book表并导入数据
# https://www.projectpro.io/recipes/connect-mysql-python-and-import-csv-file-into-mysql-and-create-table

file_path = 'BL-Flickr-Images-Book.csv'

create_book_table = """
CREATE TABLE book (
  Identifier	INT,
  Edition_Statement	VARCHAR(255),
  Place_of_Publication VARCHAR(255),
  Date_of_Publication VARCHAR(255),
  Publisher	VARCHAR(255),
  Title	VARCHAR(255),
  Author	VARCHAR(255),
  Contributors	VARCHAR(255),
  Corporate_Author	VARCHAR(255),
  Corporate_Contributors	VARCHAR(255),
  Former_owner	VARCHAR(255),
  Engraver	VARCHAR(255),
  Issuance_type	VARCHAR(255),
  Flickr_URL	VARCHAR(255),
  Shelfmarks  VARCHAR(255)
  );
 """

insert_book_values = "INSERT INTO book VALUES (%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s)"

connection = database_connection(host_name,user_name,user_password,database_name)
#execute_query(connection,'DROP TABLE book') ##删除表(调试用)
import_data(connection, create_book_table, insert_book_values, file_path) 
```

    MySQL Database connection successful
    Import successful!
    


```python
# 数据清理
to_drop = ['Edition Statement',
           'Corporate Author',
           'Corporate Contributors',
           'Former owner',
           'Engraver',
           'Contributors',
           'Issuance type',
           'Shelfmarks']

df = pd.read_csv('BL-Flickr-Images-Book.csv')
df.drop(to_drop, inplace = True, axis = 1)
df.set_index('Identifier', inplace = True)

```


```python
unwanted_characters = ['[',',','-']

def clean_datas(item):
    dop = str(item.loc['Date of Publication'])
    if dop == 'nan' or dop[0] == '[': 
        return np.NaN

    for character in unwanted_characters:
        if character in dop:
            character_index = dop.find(character)
            dop = dop[:character_index]
    return dop 

df['Date of Publication'] = df.apply(clean_datas, axis = 1)

# df['Date of Publication'].head(25)
        
```


```python
def clean_author_names(author):
# 清理作者姓名    
    author = str(author)
    
    if author == 'nan':
        return np.NaN
    
    author = author.split(',') # 根据逗号（,）分割字符串

    if len(author) == 1:
        name = filter(lambda x: x.isalpha(), author[0])
        return reduce(lambda x, y: x + y, name)

    last_name, first_name = author[0], author[1]
    
    first_name = first_name[:first_name.find('-')] if '-' in first_name else first_name
    # 如果名以'.', '.|'结尾
    if first_name.endswith(('.', '.|')):
        parts = first_name.split('.')
        
        if len(parts) > 1:
            first_occurence = first_name.find('.')
            final_occurence = first_name.find('.', first_occurence + 1)
            first_name = first_name[:final_occurence]
        else:
            first_name = first_name[:first_name.find('.')]
    
    last_name = last_name.capitalize()
    
    return f'{first_name} {last_name}'


df['Author'] = df['Author'].apply(clean_author_names)
```


```python
def clean_title(title):
    
    if title == 'nan':
        return 'NaN'
    
    if title[0] == '[': # title.statrwidth('[')
        title = title[1: title.find(']')]
        
    if 'by' in title:
        title = title[:title.find('by')]
    elif 'By' in title:
        title = title[:title.find('By')]
        
    if '[' in title:
        title = title[:title.find('[')]

    title = title[:-2]
        
    title = list(map(str.capitalize, title.split()))
    return ' '.join(title)
    
df['Title'] = df['Title'].apply(clean_title)
```


```python
pub = df['Place of Publication']
df['Place of Publication'] = np.where(pub.str.contains('London'), 'London',
    np.where(pub.str.contains('Oxford'), 'Oxford',
        np.where(pub.eq('Newcastle upon Tyne'),
            'Newcastle-upon-Tyne', df['Place of Publication'])))
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Place of Publication</th>
      <th>Date of Publication</th>
      <th>Publisher</th>
      <th>Title</th>
      <th>Author</th>
      <th>Flickr URL</th>
    </tr>
    <tr>
      <th>Identifier</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>206</th>
      <td>London</td>
      <td>1879</td>
      <td>S. Tinsley &amp; Co.</td>
      <td>Walter Forbes</td>
      <td>AA</td>
      <td>http://www.flickr.com/photos/britishlibrary/ta...</td>
    </tr>
    <tr>
      <th>216</th>
      <td>London</td>
      <td>1868</td>
      <td>Virtue &amp; Co.</td>
      <td>All For Greed</td>
      <td>A. A A.</td>
      <td>http://www.flickr.com/photos/britishlibrary/ta...</td>
    </tr>
    <tr>
      <th>218</th>
      <td>London</td>
      <td>1869</td>
      <td>Bradbury, Evans &amp; Co.</td>
      <td>Love The Avenger</td>
      <td>A. A A.</td>
      <td>http://www.flickr.com/photos/britishlibrary/ta...</td>
    </tr>
    <tr>
      <th>472</th>
      <td>London</td>
      <td>1851</td>
      <td>James Darling</td>
      <td>Welsh Sketches, Chiefly Ecclesiastical, To The...</td>
      <td>E. S A.</td>
      <td>http://www.flickr.com/photos/britishlibrary/ta...</td>
    </tr>
    <tr>
      <th>480</th>
      <td>London</td>
      <td>1857</td>
      <td>Wertheim &amp; Macintosh</td>
      <td>The World In Which I Live, And My Place In It</td>
      <td>E. S A.</td>
      <td>http://www.flickr.com/photos/britishlibrary/ta...</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.to_csv('book_fix.csv')
```


```python
file_fix_path = 'book_fix.csv'

create_book_fix_table = """
CREATE TABLE book_fix (
  Identifier	INT KEY,
  Place_of_Publication VARCHAR(255),
  Date_of_Publication VARCHAR(255),
  Publisher	VARCHAR(255),
  Title	VARCHAR(255),
  Author	VARCHAR(255),
  Flickr_URL	VARCHAR(255)
  );
 """

insert_book_fix_values = "INSERT INTO book_fix VALUES (%s,%s,%s,%s,%s,%s,%s)"

connection = database_connection(host_name,user_name,user_password,database_name)
#execute_query(connection,'DROP TABLE book_fix') ##删除表(调试用)
import_data(connection, create_book_fix_table, insert_book_fix_values, file_fix_path) 
```

    MySQL Database connection successful
    Import successful!
    


```python

alter_book = """
ALTER TABLE book
ADD FOREIGN KEY(Identifier)
REFERENCES book_fix(Identifier)
ON DELETE SET NULL;
"""

connection = database_connection(host_name,user_name,user_password,database_name)
execute_query(connection, alter_book)

```

    MySQL Database connection successful
    Query successful!
    


```python
file_bookzh_path = 'books.csv'

create_bookzh_table = """
CREATE TABLE bookzh (
  title	VARCHAR(255),
  star VARCHAR(255),
  price VARCHAR(255),
  info	VARCHAR(255)
  );
 """

insert_bookzh_values = "INSERT INTO bookzh VALUES (%s,%s,%s,%s)"

connection = database_connection(host_name,user_name,user_password,database_name)
#execute_query(connection,'DROP TABLE book') ##删除表(调试用)
import_data(connection, create_bookzh_table, insert_bookzh_values, file_bookzh_path) 
```

    MySQL Database connection successful
    Import successful!
    


```python
q1 = """
SELECT *
FROM bookzh;
"""

def read_query(connection, query):
    cursor = connection.cursor()
    result = None
    try:
        cursor.execute(query)
        result = cursor.fetchall()
        return result
    except Error as err:
        print(f"Error: '{err}'")

connection = database_connection(host_name,user_name,user_password,database_name)
results = read_query(connection, q1)

from_db = []

#for result in results:
 # print(result)
```

    MySQL Database connection successful
    

## 7. 非关系数据与MongoDB的交互实验结果

选做

## 8. 结论

了解了数据交互的基本原理、熟悉了MySQL的安装与配置、熟悉了数据交互的类型和特征、掌握了数据库存储的原理、掌握了python与数据库交互技术。

## 参考文献 

https://zhuanlan.zhihu.com/p/41631123

https://zhuanlan.zhihu.com/p/338698893

https://www.jianshu.com/p/7f4b8a97ecf0

https://www.i4k.xyz/article/sswqzx/88965166



