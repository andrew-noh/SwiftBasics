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

(a:INT, b:Int, c:Int) // Typealias


## 4) Array

Array<Type> 또는 [Type]
Array의 let과 var
Array 안에는 동일한 타입의 인스턴스가 들어가야 함

var arrayExample:Array<String> = ["A", "B", "C"]
var groups[Int] = [1, 2, 3]

+= [item]으로 append 가능

## 5) Dictionary

*값에 이름표를 붙여 저장하는 상자*

var roomCapacity:[String: Int] = ["Bansky":4, "Rivera":8]

roomCapacity["Renoir"] = 40 //값 추가하기

roomCapacity["Kahlo"]  //name에 대한 key값 불러오기

	let roomNames = [String](roomCapacity.keys) //arrys with names
	let capacities = [Int](roomCapacity.values) //keys

let total = capacities.reduce(0, combine: +)

## 6) Set

	let subway2 :Set = ["a", "b"]
	let subway3 :Set = ["b", "c"]
	
	let transfer = subway2.intersect(subway3)

## 7) IF
조건문

	if [condition] {
	
	...
	
	}
	
	else {
	
	...
	
	}

example:

	if transfer.count > 0 {
	
	print()
	
	}
	
	else {
	
	print()
	
	}

## 8) FOR

	for i = 0; i < count ; i++ {
	
	...
	
	}
	
	for item in collection {
	
	...
	
	}

## SWITCH

하나의 값에 대한 다양한 실행 매칭
default 값이 필요

	switch [value] {
	
	  case a:
	  
	  ...
	  
	  case b:
	  
	  ...
	  
	  default:
	  
	  ...
	  
	}
	
## WHERE
새로운 변수의 정의

	case ("beer", let amount) where amount > 100 :
	
## OPTIONAL

값이 없는 상태 (타입 + ?)

nil : 값이 없음을 나타냄, 모든 타입의 정수가 nil이 될 수 있음, 0 과 다름

실행중에 nil이 될 수 있는 변수에 '?' 를 붙여 특별관리하는 방법 (optional)

	var title:String = nil // 에러가 남
	var title:String? = nil //에러 나지 않음
	
	var ratings : [Int]? = nil
	var supportURL : String? = nil

## OPTIONAL 접근법

Force Unwrapping: !

값의 존재를 확신할 때 사용
	
	if ratings != nil {
		bookDescription += "has \(ratings!.count) ratings"
	}
	
## OPTIONAL BINDING

Optional Binding

if let, if var : Optional이 아닌 새로운 상수와 변수 생성

Implicitly Unwrapped Optional

선언시 ! 사용 : 구조적으로 초기화 이후 항상 값이 존재하는 경우를 위한 장치

처음에는 nil값을 가지지만 (그래서 optional 사용), 분명히 값을 가질 경우 선언 시 !를 추가하여 선언

var supportURL : String! = nil

bookDescription += "\r\nsupport web page : \(supportURL)" //supportURL에 optional을 사용할 필요 없음


## OPTIONAL BINDING EXERCISE 1

	struct WatchDevice {
	    var pairediPhone:String? //애플와치와 쌍을 이루는 아이폰의 이름.
	    var appInstalled = false //어플리케이션의 설치 유무
	
	    enum WatchSize {
	        case m42, m38
	    }
	}
	
	var appleWatch:WatchDevice? = nil
	appleWatch = WatchDevice(pairediPhone: "링고스타의 아이폰", appInstalled: true)
	
	// ①appleWatch에 대해 optional binding으로 watch라는 새로운 변수를 생성해주세요.
	if let watch = appleWatch {
	    // ②watch와 쌍을 이루는 아이폰의 이름에 대해 
	    // optional binding으로 phoneName이라는 새로운 변수를 생성해 주세요.
	    if let phoneName = appleWatch?.pairediPhone {
	        print ("AppleWatch가 \(phoneName)과 쌍을 이룹니다.")
	    }
	}

## OPTIONAL BINDING EXERCISE 2
	
	struct WatchDevice {
    var pairediPhone:String? //애플와치와 쌍을 이루는 아이폰의 이름.
    var appInstalled = false //어플리케이션의 설치 유무

    enum WatchSize {
        case m42, m38
      }
	}
	
	var appleWatch:WatchDevice! = nil
	appleWatch = WatchDevice(pairediPhone: "링고스타의 아이폰", appInstalled: true)
	
	// appleWatch에 appleWatch에 대해 optional binding으로 phoneName이라는 새로운 변수를 생성해 주세요
	if let phoneName = appleWatch?.pairediPhone {
	    print ("AppleWatch가 \(phoneName)과 쌍을 이룹니다.")
	}
		
	
