---
title: "How do you work with arrays and slices in Go?"
datePublished: Sat Apr 08 2023 13:40:29 GMT+0000 (Coordinated Universal Time)
cuid: clg80wxig01fqpxnvb6f8dker
slug: how-do-you-work-with-arrays-and-slices-in-go

---

Arrays and slices are both data types that represent a sequence of values. An array is a fixed-size data type, while a slice is a variable-size data type.

To work with arrays and slices, you need to import the "fmt" package. This package provides the Println() function, which allows you to print the contents of an array or slice.

To declare an array, you use the var keyword, followed by the array name and the data type of the array elements. For example, the following code declares an array of integers:

var myArray [5]int

To declare a slice, you use the var keyword, followed by the slice name and the data type of the slice elements. For example, the following code declares a slice of integers:

var mySlice []int

To initialize an array or slice, you use the assignment operator (=). For example, the following code initializes an array of integers:

myArray := [5]int{1, 2, 3, 4, 5}

To initialize a slice, you use the make() function. For example, the following code initializes a slice of integers:

mySlice := make([]int, 5)

To access the elements of an array or slice, you use the index operator ([ ]). For example, the following code accesses the first element of an array:

myArray[0]

To access the elements of a slice, you use the index operator ([ ]). For example, the following code accesses the first element of a slice:

mySlice[0]

To iterate over the elements of an array or slice, you use the for keyword. For example, the following code iterates over an array of integers:

for i := 0; i < len(myArray); i++ {
    fmt.Println(myArray[i])
}

To iterate over the elements of a slice, you use the for keyword. For example, the following code iterates over a slice of integers:

for i := 0; i < len(mySlice); i++ {
    fmt.Println(mySlice[i])
}