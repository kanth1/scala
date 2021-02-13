# scala
#basic of Scala

collections in scala:
Array: collection of similar type.
  we can also have Array of mixed types BUT its not receomended.
  
example:
scala> val a = Array("spark", "hive");
val a: Array[String] = Array(spark, hive)


scala> a(1)
val res5: String = hive

scala> a(0)
val res6: String = spark

scala> a(10)
java.lang.ArrayIndexOutOfBoundsException: 10
  ... 32 elided

scala> a(4) = "impala"
java.lang.ArrayIndexOutOfBoundsException: 4
  ... 32 elided

scala> a(1) = "impala"

scala> a
val res10: Array[String] = Array(spark, impala)

scala>

Scala List:
scala> val f = List(1,2,3,4,5,4,3,2,1)
val f: List[Int] = List(1, 2, 3, 4, 5, 4, 3, 2, 1)

scala> f(0)
val res0: Int = 1

scala> f.main
         ^
       error: value main is not a member of List[Int]
       did you mean map, max, min, or tail?

scala> f.min
val res2: Int = 1

scala> f(0) = 100
       ^
       error: value update is not a member of List[Int]
       did you mean updated?

scala>

NOTE: you cant modify the elements. ITS COMPLETELY IMMutable.

Importnat collection in scala:

  ARRAY:
  LIST:
  ARRAYBUFFER:
  MAP:
  Tupple:

-----------------------------
Higher Order Function : A function which can accept another function as parameter.

Higher order:
  Built 
  User defined 
  
  
MAP is builtin higher order function.

e.g.,

scala> val z = Array(1,2,3,4,5,4,3,2,1)
val z: Array[Int] = Array(1, 2, 3, 4, 5, 4, 3, 2, 1)


scala> def doubler(a : Int) : Int = {
     | val s = a*2
     | return s;
     | }
def doubler(a: Int): Int


scala> z.map(doubler)
val res1: Array[Int] = Array(2, 4, 6, 8, 10, 8, 6, 4, 2)

take every element of z and pass it to doubler.


Annonymous Function:
same e.g. with Announimious function.

scala> z.map(i=>i*2);
val res3: Array[Int] = Array(2, 4, 6, 8, 10, 8, 6, 4, 2)


scala> d.map(str => str.length)
val res4: Array[Int] = Array(5, 6, 4, 3)

scala> d.map(str => str.toUpperCase)
val res6: Array[String] = Array(SPARK, HADOOP, HIVE, PIG)

you can add "()" also: 
scala> d.map(str => str.toUpperCase());
val res7: Array[String] = Array(SPARK, HADOOP, HIVE, PIG)



