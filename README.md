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
      accsss and modify is possible. 
      cant add/remove elements
      drawback: Fixed size. both val and var. 
      
  ARRAYBUFFER:
      mutable collection.
      need to import it.
      
      scala> import scala.collection.mutable.ArrayBuffer;
        import scala.collection.mutable.ArrayBuffer
        
      scala> var cars = new ArrayBuffer[String]()
      var cars: scala.collection.mutable.ArrayBuffer[String] = ArrayBuffer()

      scala> cars += "BMW";
      val res8: scala.collection.mutable.ArrayBuffer[String] = ArrayBuffer(BMW)
      
      scala> cars += "AUDI";
      val res9: scala.collection.mutable.ArrayBuffer[String] = ArrayBuffer(BMW, AUDI)

      scala> cars += "MERCEDES";
      val res10: scala.collection.mutable.ArrayBuffer[String] = ArrayBuffer(BMW, AUDI, MERCEDES)

      scala> cars += "PORSCHE";
      val res11: scala.collection.mutable.ArrayBuffer[String] = ArrayBuffer(BMW, AUDI, MERCEDES, PORSCHE)

      scala> cars += "BUGATI";
      val res12: scala.collection.mutable.ArrayBuffer[String] = ArrayBuffer(BMW, AUDI, MERCEDES, PORSCHE, BUGATI)

      scala> cars += "ASTON";
      val res13: scala.collection.mutable.ArrayBuffer[String] = ArrayBuffer(BMW, AUDI, MERCEDES, PORSCHE, BUGATI, ASTON)  
      
     other operations:
     
     scala> cars
val res14: scala.collection.mutable.ArrayBuffer[String] = ArrayBuffer(BMW, AUDI, MERCEDES, PORSCHE, BUGATI, ASTON)

scala> cars.insert(2,"bently");

scala> cars.remove(2)
val res23: String = bently

scala> cars
val res24: scala.collection.mutable.ArrayBuffer[String] = ArrayBuffer(BMW, AUDI, MERCEDES)

scala>

so am able to add elements..
---------------------------------------------------------
MAP:
THERE IS A HOF MAP. THIS is DIFFERENT. IN THAT 'M' is small. HERE its 'M'
THIS IS A COLLECTION.

MAP(KEY,VALUE)
  1. mutable Map
  2. immutable Map - CANT ADD/REMOVE/MODIFY KEY VALAUE PAIR

scala> Map("NY" -> "NEW YORK", "NJ" -> "NEW JERSEY");
val res25: scala.collection.immutable.Map[String,String] = Map(NY -> NEW YORK, NJ -> NEW JERSEY)

scala> val mapping = Map("NY" -> "NEW YORK", "NJ" -> "NEW JERSEY");
val mapping: scala.collection.immutable.Map[String,String] = Map(NY -> NEW YORK, NJ -> NEW JERSEY)

scala> var mapping = Map("NY" -> "NEW YORK", "NJ" -> "NEW JERSEY");
var mapping: scala.collection.immutable.Map[String,String] = Map(NY -> NEW YORK, NJ -> NEW JERSEY)

scala> mapping("NJ")
val res26: String = NEW JERSEY

scala> mapping("Nj")
java.util.NoSuchElementException: key not found: Nj
  at scala.collection.immutable.Map$Map2.apply(Map.scala:298)
  ... 32 elided

scala> mapping.keys
val res28: Iterable[String] = Set(NY, NJ)

scala> mapping.values
val res29: Iterable[String] = Iterable(NEW YORK, NEW JERSEY)

scala>
scala> mapping("NY") = "NEW";
       ^
       error: value update is not a member of scala.collection.immutable.Map[String,String]
       did you mean updated?
       
       
MUTABLE MAP:
scala> var states = scala.collection.mutable.Map("NY"-> "new york", "NJ"-> "new jersey");
var states: scala.collection.mutable.Map[String,String] = HashMap(NY -> new york, NJ -> new jersey)

scala> states+= ("CA"-> "california", "WY"-> "Wyomming");
             ^
       warning: method += in trait Growable is deprecated (since 2.13.0): Use `++=` aka `addAll` instead of varargs `+=`; infix operations with an operand of multiple args will be deprecated
val res32: scala.collection.mutable.Map[String,String] = HashMap(WY -> Wyomming, NY -> new york, NJ -> new jersey, CA -> california)

scala> states
val res33: scala.collection.mutable.Map[String,String] = HashMap(WY -> Wyomming, NY -> new york, NJ -> new jersey, CA -> california)

scala>

Tupple: Collection of Heterogenious datatypes. ITS IMMUTABLE.


scala>  var tupleEx= (101, "Robert", 250000 );
var tuple: (Int, String, Int) = (101,Robert,250000)

scala>

ACCESS: tupleEx._1

we use "._" a special symbol to access.

NESTED TUPLE:
scala> var tuple=("Raghu",(20,1.33),10000);
var tuple: (String, (Int, Double), Int) = (Raghu,(20,1.33),10000)

scala> tuple._1
val res36: String = Raghu

scala> tuple._2._1
val res37: Int = 20

scala> tuple._2._2
val res38: Double = 1.33

scala>



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



