# Strings Lab 1

## Instructions for lab submission

1. Fork the assignment repo
1. Clone your Fork to your machine
1. Complete the lab
1. Push your changes to your Fork
1. Submit a Pull Request back to the assignment repo
1. Paste a link to of your Fork on Canvas and submit

## Question 1

Write code that prints out all the numbers from 1 to 10 as a single string.
(Hint: the `String()` function can convert an Int to a String)

```swift
var numStringOneToTen = ""
for i in 1...10 {
    numStringOneToTen += String(i) + " "
}
print(numStringOneToTen)
```
***
## Question 2

Write code that prints out all the even numbers from 5 to 51 as a single string.

```swift
var evenFiveToFiftyOne = ""
for i in 5...51 {
    if i % 2 == 0 {
        evenFiveToFiftyOne += String(i) + " "
    }
}
print(evenFiveToFiftyOne)
```

***
## Question 3

Write code that prints out every number ending in 4 between 1 and 60 as a single string.

```swift
var endsInFour = ""
for i in 1...60 {
    if i % 10 == 4 {
        endsInFour += String(i) + " "
    }
}
print(endsInFour)
```

***
## Question 4

Print each character in the string `"Hello world!"`

```swift
let helloWorld = "Hello world!"
for char in helloWorld {
    print(char)
}
```

***
## Question 5

Print out the last character in the string below.  You cannot use the Character literal "!" (i.e you must access `myStringSeven`'s characters).

```swift
let myStringSeven = "Hello world!"
let endStringSeven = myStringSeven.endIndex
let lastCharIndex = myStringSeven.index(before: endStringSeven)
let lastChar = myStringSeven[lastCharIndex]
print(lastChar)
```

***
## Question 6

Write code that switches on a string, given the following conditions:
- If the string's length is even, print out every character.
- If the string's length is odd, print out every other character.

```swift
let someString = "Hello world!"
var index = 0

if someString.count % 2 == 0 {
    for char in someString {
        print(char)
    }
} else {
    for char in someString {
        if index % 2 == 0 {
            print(char)
        }
        index += 1
    }
}
```

***
## Question 7

Initialize a String with a character. Show that it is a Character, and not another String, that you're using to initialize it.

```swift
var stringLetter: String = "c"
var stringChar = Character(stringLetter)
print(stringChar)
```

***
## Question 8

Build five pairs of **canonically equivalent** strings, the first of each being a pre-composed character and the second being one that uses combinable unicode scalars. Show that they are equivalent.

```swift
let aAcutePrecomposed = "\u{00E1}"
print(aAcutePrecomposed)            //prints out accented "a" with overhead `

let aAcuteDecomposed = "\u{0061}\u{0301}"
print(aAcuteDecomposed)             //prints out accented "a" with overhead `

print(aAcutePrecomposed == aAcuteDecomposed)
// prints out true because they're canonically equivalent
```
***
## Question 9

**Using only Unicode**, print out `"HELLO WORLD!"`

```swift
print("\u{0048}\u{0045}\u{004C}\u{004C}\u{004F}\u{0020}\u{0057}\u{004F}\u{0052}\u{004C}\u{0044}\u{0021}\u{00A}")
```

***
## Question 10

**Using only Unicode**, print out your name.

```swift
print("\u{004A}\u{0041}\u{0053}\u{004F}\u{004E}\u{0020}\u{0052}\u{0055}\u{0041}\u{004E}")
```
***
## Question 11

**Using only Unicode**, print out `"HELLO WORLD!"` in another language.

```swift
print("\u{0048}\u{006F}\u{006C}\u{0061}\u{0020}\u{004D}\u{0075}\u{006E}\u{0064}\u{006F}")
```

***
## Question 12

Print the below flower box using the following information.

- The unicode number for ⚘ is U-2698
- The top and bottom of the box are represented by dashes and the rows are |
- Use the terminator argument in your print statements to print on the same line.
- Hint: It may be useful to try printing out a box of just one character to start then work your way from there.

```swift
Flower Box:
- - - - - - - - - - -
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
- - - - - - - - - - -

let outerRow = String(repeating: "\u{002D} ", count: 11)
let flowerRow = String(repeating: "\u{007C}\u{0020}\u{2698}\u{0020}", count: 5) + "\u{007C}"

print(outerRow)

for numRows in 1...7 {
    print(flowerRow)
}

print(outerRow)
```

***
## Question 13

Write a program that sets up a chess board using Unicode.

```swift
Chess Board:
♖ ♘ ♗ ♕ ♔ ♗ ♘ ♖
♙ ♙ ♙ ♙ ♙ ♙ ♙ ♙




♟ ♟ ♟ ♟ ♟ ♟ ♟ ♟
♜ ♞ ♝ ♛ ♚ ♝ ♞ ♜


// White Chess Pieces with space after
var whtRook = "\u{2656}\u{0020}"
var whtKnight = "\u{2658}\u{0020}"
var whtBishop = "\u{2657}\u{0020}"
var whtQueen = "\u{2655}\u{0020}"
var whtKing = "\u{2654}\u{0020}"
var whtPawn = "\u{2659}\u{0020}"

// Black Chess Pieces with space after
var blkRook = "\u{265C}\u{0020}"
var blkKnight = "\u{265E}\u{0020}"
var blkBishop = "\u{265D}\u{0020}"
var blkQueen = "\u{265B}\u{0020}"
var blkKing = "\u{265A}\u{0020}"
var blkPawn = "\u{265F}\u{0020}"

var uniqueWhiteRow = whtRook + whtKnight + whtBishop + whtQueen + whtKing + whtBishop + whtKnight + whtRook

var uniqueBlackRow = blkRook + blkKnight + blkBishop + blkQueen + blkKing + blkBishop + blkKnight + blkRook

var rowWhitePawns = String(repeating: whtPawn, count: 8)

var rowBlackPawns = String(repeating: blkPawn, count: 8)

var emptyRow = String(repeating: "\u{0020}", count: 8)

print(uniqueWhiteRow)
print(rowWhitePawns)
print(String(repeating: emptyRow + "\u{000A}", count: 3))
print(rowBlackPawns)
print(uniqueBlackRow)

```

***
## Question 14

You are given a string stored in the variable `aString`. Create new string named `replacedString` that contains the characters of the original string with all the occurrences of the character `"e"` replaced by `"\*"`.

```swift
var aString = "Replace the letter e with *"   \\ can also use equivalent unicode
var newString = ""

for letter in aString {
    if letter == "e" {
        newString.append("*")
    } else {
        newString.append(letter)
    }
}

print(newString)
 ```

Example:

Input:
`var aString = "Replace the letter e with *"`

Expected values:
`replacedString = "R*plac* th* l*tt*r * with *"`

***
## Question 15

You are given a string stored in variable `aString`. Create a new string called `reverse` that contains the original string in reverse order. Print the reversed string.

```swift
var aString = "this string has 29 characters"
var reverse = ""

for letter in aString.reversed() {
    reverse.append(letter)
}
print(reverse)
```

Example:
Input:
`var aString = "Hello"`

Output:
`"olleH"`

***
## Question 16

You are given a string stored in variable `aString`. Print `true` if `aString` is a palindrome, and `false` otherwise. A **palindrome** is a string which reads the same backward or forward.

```swift
let aString = "anutforajaroftuna"
let reversedString = String(aString.reversed())

print(aString == reversedString)

```

Example 1:
Input:
`var aString = "anutforajaroftuna"`

Output:
`true`

Example 2:
Input:
`var aString = "Hello"`

Output:
`false`

***
## Question 17

You are given a string stored in variable `problem`. Write code so that you print each word of the string on a new line.

```swift
var problem = "split this string into words and print them on separate lines"
var currentWord = ""
var wordArray = [String] ()

for char in problem {
    if char == "\u{0020}" {
        wordArray.append(currentWord)
        currentWord = ""
        continue
    } else {
        currentWord += String(char)
    }
}

// Finishes array by appending the last value assigned to currentWord
wordArray.append(currentWord)

// Prints each element of the array onto separate lines
for eachWord in wordArray {
    print(eachWord)
}
```

Example:
Input:
`var problem ="split this string into words and print them on separate lines"`

Output:
```swift
split
this
string
into
words
and
print
them
on
separate
lines
```

***
## Question 18

You are given a string stored in variable `problem`. Write code that prints the longest word in the string.

```swift
var problem = "find the longest word in the problem description"
var currentWord = ""
var longestWord = ""
var wordArray = [String] ()

for char in problem {
    if char == "\u{0020}" {
        wordArray.append(currentWord)
        currentWord = ""
        continue
    } else {
        currentWord += String(char)
    }
}

// Finishes array by appending the last value assigned to currentWord
wordArray.append(currentWord)

for eachWord in wordArray {
    if eachWord.count > longestWord.count {
        longestWord = eachWord
    }
}
print(longestWord)




```

Example:
Input:
`var problem = "find the longest word in the problem description"`

Output:
`description`

Hint: Keep track of the longest word you encounter and also keep track of its length.

***
## Question 19

Given a string in English, create a tuple containing the number of vowels and consonants.

```swift
let vowels = "aeiou"
let consonants = "bcdfghjklmnpqrstvwxyz"
let input = "Count how many vowels I have!"

var numVowels = 0
var numConsonants = 0

for inputLetters in input.lowercased() {
    for compareWithVowels in vowels {
        if inputLetters == compareWithVowels {
            numVowels += 1
        }
    }
    for compareWithConsonants in consonants {
        if inputLetters == compareWithConsonants {
            numConsonants += 1
        }
    }
}

var vowelsToConsonants = (numVowels, numConsonants)

print(vowelsToConsonants)

```

***
## Question 20

Given a string of words separated by a `" "`. Write code that prints out the length of the last word.

If there is no last word print out `"No last word"`.

Example:
Input: `"How are you doing this Monday?"`

Output: `7`

***
```swift
var string = "How are you doing this Monday!"
var backwardsString = String(string.reversed())
var lastWord = ""

for char in backwardString {
    if char == " " {
        break
    }
    lastWord.append(char)
}
print(lastWord.count)
```
