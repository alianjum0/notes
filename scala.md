# Scala 

Scala was proposed to provide high-performance, concurrent-ready environment
for functional and object oriented programming on Java Virtual Machine platform.

* Object oriented and functional
* Statically typed
* Java compatible

Data types: `Int, Float, Double, Boolean, Char, String`

Variable: `[public] var name[:type] = value`
          `var sentence: String = "Hello World"`
          `var weight: Int= 75`
          `var condition: Boolean= true`
          `var firstChar: Char= 'a'`

Immutable Variables( or values): `[public] val name[:type] = value`
                                 `val sentense = "Hello world"`

Standard operators: 
Mathematical operators: `+,-,*,/,%`
Boolean operators: `|,&,!`


Numeric Types ->
Char          ->-> AnyVal->
Boolean       ->
                            -> Any
Collections   ->
Classes       ->-> AnyRef->
String        ->

Strings:  Multiline literals, String interpolation
val signature = "With regards,\nYour friend"
val hello = "Hello, " + "World"
val matched = (hello == "Hello, World")
val multi_line_string = """one line,
two line tabs (\t) newlines(\n),
third line"""
val approx = 344/113f // approx: Float= 3.141593
println("Pi, using 355/113, is about " + approx + ".")
println(s"Pi, using 355/113, is about ${approx}."
val repeatHi = "Hi"*5
val rep = str1*num1 //str1=cat, num=5
var sentence = "Test matching operation"
var res:Boolean  = sentence.matches("Test.*)  // regular expression
var res:String = sentence.replaceAll("m{^ ]+k","coffee")
var res:String = sentence.replaceFirst("m{^ ]+k","coffee")

5.asInstanceOf[Long]  //  convert type
(7.0/5).getClass  //  return the type of value
(5.0).isInstanceOf[Float] //  return true or false
47.toFloat  //  preferred method to convert to compatible value to<type>
# Collections: 
Array, List, Map, Tuple
Arrays: Homegeneous and Hetrogeneous
val numbers = Arrays(1,2,3)
val mix = Array(1,"Hello,10)
List:
val numbers=List(1,2,3) = 1::2::3::Nil
val mix = List(1,"Hello", 10) = 1::"Hello"::10::Nil
val listConcat = list1 ::: list2 = List.concat(list1, list2)
Map: key value pair
var mapvariable: Map[Int,String] = Map(1->"Hello")
mapvariable+= newKey -> newValue
var value = mapvariable(key) = mapvariable.get(key).get
var value = mapvariable.get(key).getOrElse(defaule value) //  get defailt value if missing
Tuples:
group of N items
items of tuples are immutable
val quadruple = (2,"orange", 0.5d, false)
println(quadruple._1 + quadruple._2 + quadruple._3 + quadruple._4)
Expressions:
val x = 5*20
val amount =x +10
is equal to
val amount = {val x=5*20; x+10}
if-then-else as expression:
val max = {if(x>y) x else y}
if -> else if -> else
# Match expression (switch):
val test: Char = 'a'
test match {
  case 'a'|'A'  => {println(Code associated with a")}
  case 'b'|'B' => {println(Code associated with b")}
}
val max = x>y match { 
    case true => x
    case false => y
}
value binding vs wildcard operator:
value binding can access value inside block
val message = "OK"
val status = message match {
    case "OK" => {println("matched OK"); 200}
    case -1   => {println("matched OK"); -1}
}
val status = message match {
    case "OK" => {println("matched OK"); 200}
    case _   => {println("matched OK"); -1}
}
Pattern guard adds an if expression:
val res:String = null
res match{
    case s if (s!= null) => println("Received " + s)
    case s => println("Error null response)
} //  s is value binding
Matching type example:
val list = List("a", 1, 'c', 34.5)
list(0) match{
    case v:String => println("String")
    case v:Int => println("Int")
    case v:Char => println("Char")
    case v=> println("Another type")
}
# Loops
- always iterate over input collection
- funtional for loop
for (i <- 0 to 3) {println(i)}  // 0,1,2,3
for (x <- 1 to 7) yield { s"Day $x:"} //("Day 1", "Day 2",...,"Day 7")
while (expression == true) {}
do {} while(expression == true)
# Console
Console.println("Hello") | println("Hello")
val line = Console.readLine() | readLine()
read* = read<type> e.g readBoolean()
versios 2 read* methods are deprecated instead
scala.io.StdIn.read* e.g scala.io.StdIn.readBoolean
val input = Console.readLine()
val vals: Array[String] = input.split("")
var name = val(0).toString
var age= val(0).toInt
readf*  //  return multiple values 
readf(String) //  return List[Any])
readf1(String)  // return one value type Any
readf2(String)  // return two value type (Any,Any)
readf* method parameter is a string that specify expected input type
"{0} {1,number}" // string and a number
"{0,number} {1,number} {2}" //  two numbers and a string
An parse exception is generated if input values are not expected data types
main problem of readf* method is all returned type are Any and needs casting
val (a,b) = Console.readf2("{0} {1,number}")
var name = a.toString
var age = b.toString.toInt
val values: List[Any] = Console.readf("{0} {1,Number})
var name= values(0).toString
var age= values(1).toString.toInt
Scala can also use java.util.Scanner but if input is not as expected an erroris
thrown
val scanner = new java.util.Scanner(System.in)
val age = scanner.nextInt()
## Functional Programming
* In pure functional programming functions are like Mathematical functions
* No side effect
* Are charactarized by set of parameters (optional)
* Perfor, calculations using only the input parameters
* Return a value
* Always return the same value for the same input
Pure function
* Do not affect any data outside the function (no side effect)
    * Do not use global variables
    * Do not change the values of its parameter
* Are not affected by any data outside the function
Only immutable objects should be used
If only pure functions are used
* The code is more stable because stateless and orthognal to external data
* Parallelization and concurrency is easier
Majority of scala functions are pure however,some non pure functions are used
def <identifier>[(<identifier:<type>,..)][:<type>] = expression
def hi = "hi" //  function returning "hi"
def multiplier(x:Int,y:Int): Int = {x*y}
def safeTrim(s:String):String = {
  if (s == null) null
  else s.trim()
}
### Procedure:
Procedure is a function with no return type
Any function end with a statement e.g println() is also a procedure
Scala compiler infer Unit type to function ending with a statement without explicit data type 
def approximate(d:Double)[: Unit] = println(f"Got Value $d%.2f")
Invoking function with an expression block
def formatDollar(amount: Double): String = amount+"$"
val res = formatDollar {val rate = 1.32; 0.235+0.7123+rate*5.32}
### Recursive functions:
def power(x:Int,n:Int):Long = {
  if (n>=1) x*power(x,n-1)
  else 1
}
### Nested functions:
def maxThree(a:Int,b:Int,c:Int) = {
  def maxTwo(x:Int, y:Int) = { if (x>y) x else y}
  maxTwo(a,maxTwo(b,c))
}
Functions can be called named parameters
    def greet(prefix:String, name:String) = prefix + " " + name
    val greeting2 = greet(name="Brown", prefix="Mr")
Functions with default value
    def greet(prefix:String= "Ms/Mr", name:String) = prefix + " " + name
Variable number of parameters **vararg**
    def sum(items: Int*): Int = {
      var total=0
      for(i <- items) {total +=1}
      total
}
### First class functions
* core value of function programming is that functions should be first class
* functions can used is any segment of the code **Functions are data types**
    * can be stored in a container e.g value, variable or data structure
    * used as a parameter or as return value from another function
function type is simply grouping from input to return type
def double(x:Int): Int = x*2
    Int         => Int
def myDouble: (Int) => Int = double // myDouble is function type (Int) to Int
println(myDouble(5))
### Higher order functions
Function that accept other functions as parameters and/or use functions as
return values are knows as **Higher order functions**
    def safeStringOp(s:String, f:String => String)={
      if(s != null) f(s)
      else s
    }
    def reverser(s:String) s.reverse
    val s1 = safeStringOp(null,reverser)y1
    val s2 = safeStringOp("test", reverser)
    def addPrefix(s:String) = "Prefix" + s
    val s3 = safeStringOp(null,addPrefix)
    val s4 = safeStringOp("test", addPrefix)
### Function literal / Anonymous functions / Lambda expressions / Lambdas
function literal is a function that lacks a name
It is assigned to a varable of immutable variable
> val doubler = (x:Int) => x*2  //  function literal
> val doubled = doubler(22)
Function literals and higher order functions
> s1 = safeStringOp(null, s=> s.reverse)
> s2 = safeStringOp("test", s=> s.reverse)
**Placeholder syntax** is shortened form of function literals replacing named
parameters with (_)
It can be used
* the explicit type of function is specified outside the literal
* the parameters are used no more than once
> val s1 = safeStringOp(null, _.reverse)
> val s2 = safeStringOp("test", _.reverse)
_ is the first paramter
**Multiple placehoder**
> def combination(x:Int, y:Int, f:(Int,Int) => Int) = f(x,y)
> combination(23,12,_-_)  //  first and second parameter of function
example wthout placehoder
> combination(23,12,(v,w)=> v - w)
## Collections
Iterate: iterate over a collection
Map: convert list item-by-item to another list
Reduce: fold a list to a single element
> val colors = List("red", "green", "blue")
> colors.foreach((c:String) => println(c))
> colors.foreach(println(_)) 
> val sizes = colors.map(_.size)
> val numbers = List(32,95,24,21,17)
> val numberTimes2 = numbers.map( (n:Int) => n*2 )
> val numberTimes2 = numbers.map( _*2 )
> val sum = numbers.reduce( (n1:Int,n2:Int) => n1+n2 )
> val sum = numbers.reduce( _+_ )
> val concatenated = colors.reduce( _ + _ )
### Other mapping operations
> List(0,1,0).collect({case 1=> "ok"}) Transform only matched elements
> List("m,t","a").flatMap(_.split(',')) Transform each element and flatten list
> List("milk","tea").map(_.toUpperCase) Transform each elemnet with function
### Other reducing operations
> List(4,5,6).reduce(_+_) Reduce list starting with first element
> List(4,5,6).reduceLeft(_+_) Reduces left to right starting from first element
> List(4,5,6).reduceRight(_+_) Reduces right to left starting from first element
> List(4,5,6).fold(0)(_+_) Reduces the list given the starting value
> List(4,5,6).foldLeft(0)(_+_) Reduces list left to right  given the starting value
> List(4,5,6).foldRight(0)(_+_) Reduces list right to left given the starting value
> List(4,5,6).scan(0)(_+_) Returns a list of each accumulated value
> List(4,5,6).scanLeft(0)(_+_) Returns a list accumulated value left to right
> List(4,5,6).scanRight(0)(_+_) Returns a list accumulated value right to leftt
### Math reduction operations
> List(45,59,26).max
> List(45,59,26).min
> List(45,59,26).product
> List(45,59,26).sum
### Boolean reduction operations
> List(45,59,26).contains(29)
> List(45,59,26).endsWith(List(59,26))  Check if list ends with a given list
> List(45,59,26).exists(_<18) Check if true for atleast 1 element
> List(45,59,26).forAll(_<18) Check if hold true for all
> List(45,59,26).startsWith(List(45)) Check if starts with list
### Other operations on lists
> List(45,59,26).distinct Return list without duplicates
> List(45,59,26).filter(_<18)
> List(45,59,26).partition(_<3) Groups element into a tuple of two lists
> List(45,59,26).reverse
> List(45,59,26).drop(2)  drop first n elements from list
## Object Oriented Programming
* object is scala is used to define singleton class
* static method and field doest not exist but can be achieved by object
> object HelloWorld{
>   def main(args:Array[String]): Unit = {
>     println("Hello World")
>   }
> }
Class
> class FirstClass{
>  /* variables and methods */
>   def add(x:Int, y:Int):Int = {
>     return x+y
>   }
> }
> var fc = new FirstClass
> var fc = new FirstClass()
Methods
> def add(x:Int,y:Int):Int = { x+y }
> def add(x:Int,y:Int):Int =  x+y 
method returning nothing
> def print2Times(text: String) {
>   println(text)
>   println(text)
> }
> var myObj = new FirstClass
> myObj.add(2,3)
> myObj add(2,3)
> override def toString = { /* new code */}
### Constructors
* All classes have primary constructors
* Auxiliary Constructors are optional
The signature of primary constructor are listed after the class name
code of primary constructor is the entire body of the class.
### Primary Constructor
* defines a private attribute for each primary Constructor parameter
* for val type creates a public read type method
* for var type also creates a public write type method 
* if private before a parameter read and write method are not generated
> class PersonProfile(var name:String, var surname:String, var title:String,
>   var age:Int){ println("Hi " + name) } 
> object TestConstructor{
>   def main(args: Array[String]): Unit = {
>     var pp = new PersonProfile("Paola", "Garza", "Mr", 40)
>     println("Hello " + pp.title + " " + pp.name + " " + pp.surname + " ")
>     println("You are " + pp.age + " years old")
>   }
> }
### Auxiliary Constructor
* Every class can have multiple auxiliary constructors
> def this([list of parameters]) = { /* call to primary constructor, code */}
* all the primary constructor parameters must be initialized
1. Auxiliary constructor with first three parameters and age as -1
2. Auxiliary constructor with title "" and age -1
> class PersonProfile(var name:String, var surname:String, var title:String,
>   var age:Int){
>   def this(name:String, surname: String, title: String)={
>     this(name,surname,title,-1)
>   }
>   def this(name:String, surname: String)={
>     this(name,surname,""1)
>   }
> } 
### Companion Objects

