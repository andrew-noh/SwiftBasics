# SwiftBasics
Swift basic tutorial notes


## 1) Var  &  Let

var  //변수, mutable
let  //상수, immutable/unchangable


## 2) Data types

:String  //String type text
//"\()" 괄호 안에 val/let 넣어서 string 사이에 입력 가능
//.hasPrefix   .hasSuffix method 로 T/F value return 가능

:Double  //기본 64-bit floating-point number

:Float  //32-bit floating-point number ex. 3.14159

:Int  //Integer(정수)

:UInt  //양의 정수(0 ~ 255)

let minValue = UInt8.min  // minValue is equal to 0, and is of type UInt8
let maxValue = UInt8.max  // maxValue is equal to 255, and is of type UInt8

.max method  //maximum value
.min method  //minimum value

## 3) Tuple

Tuple  //코마로 구분된 값의 리스트

let tupleExample:(a:INT, b:Int, c:Int) = (1, 2, 3)

(a:INT, b:Int, c:Int) //typealias


## 4) Array

Array<Type> 또는 [Type]
Array의 let과 var
Array 안에는 동일한 타입의 인스턴스가 들어가야 함

var arrayExample:Array<String> = ["A", "B", "C"]
var groups[Int] = [1, 2, 3]

+= [item]으로 append 가능
