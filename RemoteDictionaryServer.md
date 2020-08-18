
Redis :

What is Redis?

-Redis stands for REmote DIctionary Server.

Remote- Distributed

Dictionary - 
  Data Structure
      Organization of data based on structure.
      
  Objective of Data Structure :
    - Store - write
    - Process
    - Report -read

  Store:
     1.Persistent : Permanent
       -Disk store
          -Files
             -Structured
                    -Database Management System.
			            -SQL-----------------------Reading,Processing,Write
             -Unstructured
                    -NO SQL Movement
		    -Big Data
     2.In Memory : not permanent

In Memory Data Structure
   Storing data inside RAM
   Read data from RAM
   Processing data from RAM.

--Types of Data Structure
  1.single dimension
     Array
        -Collection of data
            -Ordered based on index
            -index is location (memory address)
       Subsets of Array
	 -List : Dynamic Data Structure
           SubSet of List
		-LinkedList
                -Stack
                -Queue
                -Set
                  -SortedSet
  2.two dimension
       Key-Value Pair
   
   Dictionary
      Other Names
     ->Hash table
     ->Map
**************************************XXXXXXXX************************************


Redis is written in c language.

Redis distribution:
-open source - redis.io
-enterprise - redis labs


1.Redis Server
2.Redis client /Redis cli
  
Redis-Server is application which is running on "Redis-Runtime"
    - Provides Remote Dictionary Server - Distributed in memory data structure.
Redis-cli is application which is running on "redis-cli runtime"
    - Communication channel, to communicate Redis Server

--------------------------------XXXXXXXXX-----------------------------------------

Redis is reference implementation of  no sql Databases

Types of NoSql database
- Key-Value
- Document 
- Column Family
- Graph 

Redis is  MultiModel.

Relational database stores data in the form of tables(columns +rows)
- Column is a mapper for storing data.
- In Relational model : schema is fixed.
- NoSql schema is dynamic/flexible.
- Redis is at core level is KEY-VALUE database.

Redis can be fine tuned for other patterns like document oriented
 - Redis can be used like mongo.

Redis has concept called "Redis Modules" which is plug able architecture , where we can plug  Modules on top of redis to extends Redis core functionality.
&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&
Redis is a multi purpose data store

-Used as Database
-Used as Cache
-Used as Message Bus / PUB-SUB Engine
.................................................................................

Redis Features:
&&&&&&&&&&&&&&
1. Supports strings,hashes,lists,sets,sorted sets,bitmaps,hyperloglogs,geospatial.
2. Built-in replication.
3. Lua scripting.
4. Transactions.
5. Automatic partitioning with Redis Cluster.
6. Transactions
7. Pub/Sub
8. Keys with a limited time-to-live
9. LRU eviction of keys
10. Automatic failover

&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&
Redis Storage Architecture &&  Persistency:
...........................................

Redis is the best for storing data in RAM - in memory.
This feature makes Redis for Enterprise application Cache architecture.


 What about machine restarts  after storing data?
   All data will be lost.

What about durability?

 Redis has concept persistency

 Redis stores /takes snapshot of data inside disk file called "fileName.rdb" or "fileName.aof"

Redis server is program, which can be started without any input- redis starts with default configuration.

Redis high level configuration:

 Redis offers lot of configuration files

->redis-conf -https://raw.githubusercontent.com/redis/redis/6.0/redis.conf
->sentinel.conf

redis-conf:
...........

Category:

1.network
2.general
  databases 16
3.snapshot
4.Replication
5.Security
6.clients
7.Memory Management
8.Lazy freeing
9.AOF Mode 
10.Lua scripting
11.High Availability
    ->Cluster
    ->Cluster with Docker/NAT
12.Slow Log
13.Latency Monitor
14.Messaging
    ->Event Notification
15.Advanced config

Note:

   How redis server can be extended
  
 1.Via config file
     redis.config
      port 7777
 2.Via Command line
      $redis-server --port 7777
 

Note:
 Redis stores data inside heap memory of redis process, in turn they maintain structure called
 "redis-database" which is memory layout for storing key-values

 by default redis offers 16 segment of database.

 Which can be selected by using a command "select" from redis cli

 $ select 1
 $ select 10

snapshot: Persistency

&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&
Programming with Redis:
......................
 Redis stores data in memory using data structure.

Data is stored inside redis using data type like rdbms sql column types.

sql 

 create table customer(id number,name varchar2(10);

in redis key-value

key has type

value has type

key type :

  string: binary safe: 
    not only characters but you can store binary/byte representation.
in general key is string.

value type:
 »»Strings
 »»Lists
 »»Sets
 »»Sorted sets
 »»Hashes
 »»Bit arrays
 »»Streams
 »»HyperLogLogs

 
Syntax
  key value 

  Note: redis has no Explicit type.

 How to represent type of a value.

  -> based on input(data)
       string and numbers
       hello    1

 ->via command
    rpush value
         It stores data inside List data structure

 how to send /get  Data?
  
   commands: 
     commands are classified based on data type.
....................................***************........................................

How do i send command?

 Via Client Programms.

Redis offers a client program called "redis-cli" through which you can send commands.

Redis architecture defines client-server paradigm.
     Redis uses request-response model.

  In web env
   Client(browser)---send request----------->webserver
                  <-------response-----------
                      using HTTP Channel
  In redis
   Redis client ----send request(set of commands) ----Redis server
		<--------response(Reply)-------------
			Using TCP/IP protocol


  Redis clients:
   Redis has been extended with various programming languages
  Java,Javascript,python,c++,C#,go......

  Every programming language offers "Drivers" to connect redis
 
................................................................................
Lets code:
..........
cli
 redis-cli

Strings

1.Redis Strings are binary safe, this means that a Redis string can contain any kind of data, for instance a JPEG image or a serialized Ruby/JSON object.
2.A String value can be at max 512 Megabytes in length
3.String is collection of bits :
   

 "Internally string is array of bits:Byte array".


String sub types: String can be used to represent other types

1.number : integer
2.decimals : floats

String commands:

 set command
 get command

String apis(commands)

1.set,get
2.append
3.strlen
3.getrange
4.setrange

Numerical Values:

1.incr
2.incrby
3.decr
4.decrby
5.incrbyfloat

BitMaps
 setbit

 &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&

 Lab:
 redis-cli 

 java
 -jedis
 -lettuce

 spring boot

 &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&

 Jedis:

 Setup java maven Project:
 pom.xml
     <dependencies>
        <dependency>
            <groupId>redis.clients</groupId>
            <artifactId>jedis</artifactId>
            <version>2.9.0</version>
        </dependency>
    </dependencies>

Testing Connection:
package com.mycom.jedis;

import redis.clients.jedis.Jedis;

public class HelloWorldJedis {
    public static void main(String[] args) {
        Jedis jedis = new Jedis("localhost", 6379);
        System.out.println(jedis.ping());

    }
}
Strings:
.......
set and get:
package com.mycom.jedis.types;
import redis.clients.jedis.Jedis;

public class StringsKeyDemo {
    public static void main(String[] args) {
        Jedis jedis = new Jedis("localhost", 6379);
        //strings
        //set and get
        System.out.println(jedis.set("name","Subramanian"));
        System.out.println(jedis.get("name"));


    }
}
Lists:
package com.mycom.jedis.types;

import redis.clients.jedis.Jedis;

public class Lists {
    public static void main(String[] args) {
        Jedis jedis = new Jedis("localhost", 6379);
        jedis.lpush("queue#tasks", "firstTask");
        jedis.lpush("queue#tasks", "secondTask");
        System.out.println(jedis.rpop("queue#tasks"));
    }
}

Sets:
package com.mycom.jedis.types;

import redis.clients.jedis.Jedis;

import java.util.Set;

public class SetsDemo
{
    public static void main(String[] args) {
        Jedis jedis = new Jedis("localhost", 6379);

        jedis.sadd("nicknames", "nickname#1");
        jedis.sadd("nicknames", "nickname#2");
        jedis.sadd("nicknames", "nickname#1");

        Set<String> nicknames = jedis.smembers("nicknames");
        System.out.println(nicknames);
        boolean exists = jedis.sismember("nicknames", "nickname#1");
        System.out.println(exists);

    }
}
SortedSet:
package com.mycom.jedis.types;

import redis.clients.jedis.Jedis;

import java.util.HashMap;
import java.util.Map;

public class SortedSetDemo {
    public static void main(String[] args) {
        Jedis jedis = new Jedis("localhost", 6379);

        Map<String, Double> scores = new HashMap();

        scores.put("PlayerOne", 3000.0);
        scores.put("PlayerTwo", 1500.0);
        scores.put("PlayerThree", 8200.0);

        scores.entrySet().forEach(playerScore -> {
            jedis.zadd("ranking", playerScore.getValue(), playerScore.getKey());
        });
        String player = jedis.zrevrange("ranking", 0, 1).iterator().next();
        long rank = jedis.zrevrank("ranking", "PlayerOne");
        System.out.println(player + " " + rank);
    }
}
Hashes:
package com.mycom.jedis.types;

import redis.clients.jedis.Jedis;

import java.util.Map;

public class HashesDemo {
    public static void main(String[] args) {
        Jedis jedis = new Jedis("localhost", 6379);

        jedis.hset("user#1", "name", "Peter");
        jedis.hset("user#1", "job", "politician");

        String name = jedis.hget("user#1", "name");

        Map<String, String> fields = jedis.hgetAll("user#1");
        System.out.println(fields);
    }
}


Spring Boot:

-Spring boot uses redis-data starter to abstract redis access.
-Spring boot can use jedis / lettuce as wrapper /driver around Spring.

-RedisAutoConfiguration class provides default configuration to redis, so we need to write any configuration by default. if you want to add extra configuration.


@Configuration
class AppConfig {

  @Bean
  public JedisConnectionFactory redisConnectionFactory() {
    //changes will go here
     return new JedisConnectionFactory();
  }
}

When you run after adding this configuration you may get error.

Caused by: java.lang.ClassNotFoundException: redis.clients.jedis.JedisPoolConfig.

JedisPoolConfig is needed when we use Jedis Configuration. In Spring Boot 2.0, spring-boot-starter-data-redis gives Lettuce dependency by default instead of Jedis. To use Jedis configuration, exclude Lettuce and add Jedis as following.

<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-data-redis</artifactId>
  <exclusions>
    <exclusion>
     <groupId>io.lettuce</groupId>
     <artifactId>lettuce-core</artifactId>
    </exclusion>
  </exclusions>           
</dependency>       
<dependency>
  <groupId>redis.clients</groupId>
  <artifactId>jedis</artifactId>
</dependency>

Working with Objects through RedisTemplate:
...........................................

- Like other templates technique in Spring, spring offers redis template to connect with Redis 
- The template offers a high-level abstraction for Redis interactions.
- While RedisConnection offers low-level methods that accept and return binary values (byte arrays), the template takes care of serialization and connection management, freeing the user from dealing with such details.

-Moreover, the template provides operations views that offer rich, generified interfaces for working against a certain type or certain key 

Redis Template Operations:

GeoOperations

    Redis geospatial operations, such as GEOADD, GEORADIUS,…​

HashOperations

    Redis hash operations

HyperLogLogOperations

    Redis HyperLogLog operations, such as PFADD, PFCOUNT,…​

ListOperations

    Redis list operations

SetOperations

    Redis set operations

ValueOperations

    Redis string (or value) operations

ZSetOperations

    Redis zset (or sorted set) operations

Key Bound Operations
.....................
BoundGeoOperations

    Redis key bound geospatial operations

BoundHashOperations

    Redis hash key bound operations

BoundKeyOperations

    Redis key bound operations

BoundListOperations

    Redis list key bound operations

BoundSetOperations

    Redis set key bound operations

BoundValueOperations

    Redis string (or value) key bound operations

BoundZSetOperations

    Redis zset (or sorted set) key bound operations

&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&

List Operations:
................
List is used to store sequence of strings /items

List can be used to implement various data structures
-queue
 - first in first out
add first, get first

add and remove
view items
view length of the queue

RPUSH - Right push
LPOP  - left pop
 -simple queue
LRANGE - Get list of iitems first 5 items.

ListOperations<String, String> operations = this.template.opsForList();
        //queue
operations.leftPush("playlist","100");
operations.leftPush("playlist","200");
operations.range("playlist",0,operations.size("playlist")).forEach(i->log.info(i));
-stack : LAST in first Out

RPOP key


List Pointers:

- Redis's Lists are linked lists, therefore insertions and deletions from the beginning or the end of a List run in O(1), constant time.

- The task of accessing an element in a List runs in O(N), linear time, but accessing the first or last element always runs in constant time.

- The maximum number of elements a List can hold is 232-1, which means there can
 be more than 4 billion elements per List.

Some real-world use cases of Lists are as follows:
• Event queue: Lists are used in many tools, including Resque, Celery,
and Logstash
• Storing most recent user posts: Twitter does this by storing the latest tweets
of a user in a List

&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&
Hashes:
.......
Looks like json, java hashMap,python dictionary
Redis hashes are mutable
  -add,remove,change,increment

It is collection of fields. We can add and remove fields as needed.
Redis hashes schema less.

eg:
HSET key field value field value field value field value
HSET player:1 name subramanian race ELF level 4 hp 20 gold 20

















