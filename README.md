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
