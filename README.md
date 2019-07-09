# Optionals lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1√

`var userName: String?`

Write 3 different ways of safely unwrapping and printing the value of `userName`.  If it is nil, print "No name".

- Method one: Check for nil and force unwrap
```swift
var userName: String?
if userName != nil{
print(userName!)
}
```

- Method two: Optional binding
```swift
//OPTIONAL BINDING
if let myUserName = userName {
print(myUserName)
}
```

- Method three: Nil coalescing
```swift
let userName2 = userName ?? "It is recommended to add a user name "
```


## Question 2√

Given optional string `backgroundColor`, write code that safely unwraps and prints it. If backgroundColor is nil, give it a value.

`var backgroundColor: String?`

```swift
backgroundColor = "blue"
if let myColor = backgroundColor {
print ("my favorite color is \(myColor)")
}else {
print("Sorry you have have a backGroundColor saved")
}
```
OR

```swift

var backgroundColor: String?

if backgroundColor != nil{
print (backgroundColor!)
}else {
backgroundColor = "purple"
}
print(backgroundColor!)
```
OR

```swift
let myNewColor = backgroundColor ?? "Brown"
print(myNewColor)
```

## Question 3√

Given an optional width and an optional height of a rectangle, write code that calculates and prints the area. Print an error message if either value is nil.

```swift
var width: Double?
var height: Double?
```
```swift
var width: Double?
var height: Double?
var area = (Double)()

if let width = width {
if let height = height {
area = (width * height)
print(area)
}
}else {
print ("fatal error")
}
```
```swift
var width: Double?
var height: Double?
var area = (Double)()

if  width == nil || height == nil {
print ("fatal error")
}else {
area = width! * height!
}
print(area)

```

## Question 4 √

Given the following optional variables `name`, `age` and `height`. Write code so that it prints `name`, `age` and `height` if they all have a value. If any are nil, print an error message. Try using optional binding.

```swift
var name: String?
var age: Int?
var height: Double?
```
```swift 
var name: String?
var age: Int?
var height: Double?

if let myName = name {
print(myName)
}else {
print("Error, you dont have a name value")
}

if let myAge = age {
print(myAge)
}else {
print("Error, you dont have an age value")
}

if let myHeight = height {
print(myHeight)
}else {
print("Error, you dont have a height value")
}

```
OR

```swift 

var name: String?
var age: Int?
var height: Double?

if let myName = name {
if let myAge = age {
if let myHeight = height{
print ("Name: \(myName)\nAge: \(myAge)\nHeight: \(myHeight)")
}else {
print("Error, missing a value")
}

} else{
print("Error, missing a value")
}
}else {
print("Error, missing a value")
}
```

## Question 5√

Given the variables `firstName`, `middleName` and `lastName`. Create a variable called `fullName` that is a nicely formatted string.

```swift
var firstName: String = "Johnny"
var middleName: String?
var lastName: String = "Stone"
```

```swift
var fullName:String = "\(firstName) \(middleName ?? "") \(lastName)"
print(fullName)
```

## Question 6√

Write code that adds 15 to `myIntString`, then prints the sum. Use the `Int()` constructor which returns an optional Int `(Int?)`.

`let myIntString = "35"`

```swift

// using OPTIONAL BINDING

let myIntString = "35"
let plus15 = 15
var newValue = (Int)()

if let value = Int(myIntString){
newValue = value + plus15
}
print(newValue)
```
OR

```swift

//using FORCE UNWRAPPING
let myIntString = "35"
let plus15 = Int(myIntString)! + 15
```


## Question 7√

Given an optional tuple of optional Ints, write code to safely unwrap the tuple and calculate the sum of its contents that aren't nil.

```swift
var scores: (Int?, Int?, Int?)?

var testCaseOne = (4, nil, 7)
var testCaseTwo = (nil, nil, 9)
var testCaseThree = (5, 10, 24)
```
```swift
var testCaseOne:(Int?, Int?, Int?)? = (4, nil, 7)
var testCaseTwo:(Int?, Int?, Int?)? = (nil, nil, 9)
var testCaseThree:(Int?, Int?, Int?)? = (5, 10, 24)

var testOne = Int()
var testTwo = Int()
var testThree = Int()
if let caseOne = testCaseOne, let caseTwo = testCaseTwo, let caseThree = testCaseThree {
if let value1 = caseOne.0{
testOne +=  value1
}
if let value1 = caseOne.1{
testOne +=  value1
}
if let value1 = caseOne.2{
testOne +=  value1
}
if let value1 = caseTwo.0{
testTwo +=  value1
}
if let value1 = caseTwo.1{
testTwo +=  value1
}
if let value1 = caseTwo.2{
testTwo +=  value1
}
if let value1 = caseThree.0{
testThree +=  value1
}
if let value1 = caseThree.1{
testThree +=  value1
}
if let value1 = caseThree.2{
testThree +=  value1
}
}

print ("\(testOne) \(testTwo) \(testThree)")
```

OR
```swift
let testCaseArray = [testCaseOne,testCaseTwo,testCaseThree]

for testCaseTuple in testCaseArray{
var score = Int()
if let testCaseScore = testCaseTuple {
if let scoreInt = testCaseScore.0{
score += scoreInt
}
if let scoreInt = testCaseScore.1{
score += scoreInt
}
if let scoreInt = testCaseScore.2{
score += scoreInt
}
}
print(score)
}
```


## Question 8√

Safely unwrap `tuple` if there’s a non-nil tuple value and print it out.

```swift
var tuple: (Int, Int)?
if Bool.random() {
 tuple = (5, 3)
}
```
```swift

if let tupleValue = tuple {
print(tupleValue)
}
```


## Question 9√

Write code that either doubles `myInt` and then prints it, or prints an error message if myInt is nil.

```swift
let myInt: Int?
if Bool.random() {
 myInt = 5
}
```
```swift

// myInt kept giving an error saying (myInt constant used before being assigned. to fix this issue, i changed it from a (let) to a (var). that fixed the error problem, allowing the code to run.

var myInt: Int?
if Bool.random() {
myInt = 5
}

var myInt2X = Int()

if let doubledValue = myInt {
myInt2X = doubledValue + doubledValue
print(myInt2X)
}else {
print("mtInt doesnt have a value assigned to it")
}
```

## Question 10√

Write code that prints out the product of `myDouble` and `doubleTwo` or prints an error message if `myDouble` is nil.

```swift
var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
 myDouble = 12
}
```

```swift
var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
myDouble = 12
}

if let valueOfMyDouble = myDouble {
print(valueOfMyDouble * doubleTwo)
}else {
print("Sorry missing a value")
}
```
OR

```swift
// Using a range and also storing the value for latter use. maing it more dynamic to geneate random results.

var myDouble: Double?
let doubleTwo: Double = 5
var range = 1...100
var result:Double = Double()

if Bool.random() {
myDouble = Double(range.randomElement()!)
}

if let valueOfMyDouble = myDouble {
result = valueOfMyDouble * doubleTwo
print(result)
}else {
print("Sorry missing a value")
}
print(result)
```


## Question 11√

Determine if the variable contains a Boolean or nil value. If nil set the variable to false, else keep it true.

```swift
var isTheGreatest: Bool?

if Bool.random() {
 isTheGreatest = true
}
```
```swift
var isTheGreatest: Bool?

if Bool.random() {
isTheGreatest = true
}

if let value = isTheGreatest {
print(value)
}else {
isTheGreatest = false
print(isTheGreatest!)
}
```


## Question 12 √

Given the code below print the sum of each non-nil element in `myTuple`.

 ```swift
 var myTuple:(Int?, Int?, Int?, Int?)
 var sumTuple = (Int)()
 
 if Bool.random() {
 myTuple.0 = 5
 myTuple.2 = 14
 } else {
 myTuple.1 = 9
 myTuple.3 = 10
 }
 
 if let tuples = myTuple.0 {
 sumTuple += tuples
 }
 if let tuples = myTuple.1 {
 sumTuple += tuples
 }
 if let tuples = myTuple.2 {
 sumTuple += tuples
 }
 if let tuples = myTuple.3 {
 sumTuple += tuples
 }
 print(sumTuple)
```


## Question 13√

Given the helper functions and code below, check to see if your `evolutionaryStone` is able to evolve your pokemon.  The table below shows the appropriate matches of pokemon to stone:

| Pokemon	   | Stone    |
| :--------: | :------: |
| Pikachu	   | Electric |
| Bulbasaur	 | Grass    |
| Charmander | Fire     |
| Squirtle	 | Water    |


```swift
// Helper Functions

func eStone() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Electric"
 case 1:
  return "Grass"
 case 2:
  return "Fire"
 case 3:
  return "Water"
 default:
  return "No Stone"
 }
}

func starterPokemon() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Pikachu"
 case 1:
  return "Bulbasaur"
 case 2:
  return "Charmander"
 case 3:
  return "Squirtle"
 default:
  return "Not a Pokemon"
 }
}

let pokemon: String?
var evolutionaryStone: String?
pokemon = starterPokemon()
evolutionaryStone = eStone()
```
```swift
let pokemon: String?
var evolutionaryStone: String?
pokemon = starterPokemon()
evolutionaryStone = eStone()

if let check = pokemon {
if let check2 = evolutionaryStone {
if check == "Pikachu" && check2 == "Electric" {
print("You can use \(check2) stone to evolve \(check)")
} else if check == "Pikachu" && check2 != "Electric"{
print("You can NOT use \(check2) stone to evolve \(check)")
}
if check == "Bulbasaur" && check2 == "Grass" {
print("You can use \(check2) stone to evolve \(check)")
} else if check == "Bulbasaur" && check2 != "Grass"{
print("You can NOT use \(check2) stone to evolve \(check)")
}
if check == "Charmander" && check2 == "Fire" {
print("You can use \(check2) stone to evolve \(check)")
}else if check == "Charmander" && check2 != "Fire"{
print("You can NOT use \(check2) stone to evolve \(check)")
}
if check == "Squirtle" && check2 == "Water" {
print("You can use \(check2) stone to evolve \(check)")
}else if check == "Squirtle" && check2 != "Water"{
print("You can NOT use \(check2) stone to evolve \(check)")
}
if check == "Not a Pokemon" || check2 == "No Stone" {
print("You cant use \(check2) stone to evolve \(check)")
}
}
}
```

## Question 14√

Given an optional int `numberOfPeople`, write code that unwraps and prints it **only if it is even**. Try using optional binding with a condition.

```swift
var numberOfPeople: Int?

if Bool.random() {
 numberOfPeople = 108
}
```
```swift
if let evenNum = numberOfPeople {
if evenNum % 2 == 0{
print(evenNum)
}else {
print("number value is odd")
}
} else {
print("number value is nil")
}

```

## Question 15√

Given the array of optional Ints `someNumbers`, write code to find the product of the array not including any nil values.

```swift
var someNumbers: [Int?] = []

for i in 0..<20 {
    someNumbers.append(Bool.random() ? i : nil)
}
```

```swift
var someNumbers: [Int?] = []
var result = [Int?]()
var finalResult = 1

for i in 0..<20 {
someNumbers.append(Bool.random() ? i : nil)
}
//print(someNumbers)
for i in someNumbers{
if let number = i {
result += [number]
}
}

print(result)
for i in result{
if let newResult = i {
finalResult *= newResult
}
}
print(finalResult)
```
```swift
var someNumbers: [Int?] = []
var result = [Int]()
var finalResult = 1

for i in 0..<20 {
someNumbers.append(Bool.random() ? i : nil)
}
//print(someNumbers)
for i in someNumbers{
if let number = i {
result += [number]
}
}

for i in result {
finalResult *= i
}
print(finalResult)
```

## Question 16√

Given the array `poorlyFormattedCityNames`, create a new array with the city names capitalized and any nil values removed.

```swift
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]

Output: ["New York", "Boston", "Chicago", "Los Angeles", "Dallas"]
```
```swift
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas"]
var capitalizeChar: [String] = []

for i in poorlyFormattedCityNames{
if let value = i {
capitalizeChar += [value.lowercased().capitalized]
}
}
print(capitalizeChar)
```


OR
```swift
let nonNilElements = poorlyFormattedCityNames.filter { $0 != nil }
var lowerCased :[String] = []
var capitalize: [String] = []

for i in nonNilElements {
if let value = i {
lowerCased += [value.lowercased()]
}
}
for i in lowerCased{
capitalize += [i.capitalized]
}
print(capitalize)

```

OR

```swift
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas"]
var lowerCased :[String] = []
var capitalize: [String] = []

for i in poorlyFormattedCityNames{
if let value = i {
lowerCased += [value.lowercased()]
}
}

for i in lowerCased{
capitalize += [i.capitalized]
}
print(capitalize)

```

## Question 17√

Given a random array of optional numbers, create a new array of all the even numbers that aren't nil.

```swift
var aBunchOfNumbers: [Int?] = []

for _ in 0..<20 {
 aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}
```
```swift
for i in aBunchOfNumbers{
if let validNum = i {
if validNum % 2 == 0{
evenValues += [validNum]
}
}
}
print(evenValues)

```


## Question 18√

Given the following array of zip codes as strings, write code that turns them into an array of Ints.

`let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]`

```swift
let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]
var zipCodeInts = [Int]()

for zipcode in zipCodeStrings {
var holder = Int(zipcode)
if let value = holder {
zipCodeInts += [value]
}
}
print(zipCodeInts)
```


## Question 19√

Some students were asked some questions about their favorite foods and colors and the answers were stored in an array `studentInfo`.

- Print the names of the students that do not have a favorite color.

- Print the names of the students that don't have a favorite color or a favorite food.

- Create a new array of type `[(String, String, String)]` that contains the students with both favorite colors and foods.

`let studentInfo: [(String, String?, String?)] = [("Bill", "Burgers", "Blue"), ("Rita", nil, "Red"), ("Peter", "Pizza", "Purple"), ("Sarah", "Sandwiches", nil), ("Jeff", nil, nil), ("Lucy", "Leftovers", "Lilac"), ("Mike", "Meat", "Mauve"), ("Gemma", nil, "Green")]`

```swift
var allValue:[(String, String, String)] = []

for info in studentInfo {
if info.2 == nil {
print("\(info.0) does not have a favorite color")
}
if info.1 == nil && info.2 == nil {
print("\(info.0) does not have a favorite food nor a favorite color")
}
if let favFood = info.1 {
if let favColor = info.2 {
allValue += ([(info.0, favFood, favColor)])
}
}
}
print(allValue)

```

## Question 20√

Given an optional array of optional tuples of optional UInt8s,

- Write code to safely unwrap and print the tuples in the array with all 3 RGB values.

- Write code that counts all the nil values.

`let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? = [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]`

```swift
var nilCounter = 0

for i in possibleColors!{

if i == nil{
nilCounter += 1
}
if i == nil {

}
if let tuple = i {
if let index = tuple.r {
print("r: \(index)")
} else {
nilCounter += 1
}
if let index = tuple.g {
print("g: \(index)")
}else {
nilCounter += 1
}
if let index = tuple.b {
print("b: \(index)")
}else {
nilCounter += 1
}
}
}

print("There are \(nilCounter) nil values")
```


## Question 21√

Consider the following nested optional. It corresponds to a number inside a box inside a box inside a box.

- Fully force unwrap and print number.

- Optionally bind and print number.

`let number: Int??? = 10`

```swift
// FORCE UNWRAPPING
let number: Int??? = 10
var value = number!!!
print(value)

//OPTIONAL BINDING
if let i = number{
if let j = i {
if let value = j {
print(value)
}
}
}
```

## Question 22

Given an Array of Optional Strings, write code that concatenates all non-nil values together except for strings with 3 or more vowels.

`let monkeyingAround = ["orangutan", "apes",nil, "monkeys", "gorillas", "lemurs", nil]`

output: `"apesmonkeyslemurs"`


## Question 23

Given the value below, print out all of the non-nil Ints it contains by accessing each of them.

`var strangeStructure: ([Int]?, [[Int?]], [[Int]?], Int)? = ([1], [[2,3,4],[],[5,nil],[nil]], [nil, [6,7,8],nil,[],[9]], 10)`
