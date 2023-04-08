---
title: "How do you create and use interfaces in Go?"
datePublished: Sat Apr 08 2023 13:40:32 GMT+0000 (Coordinated Universal Time)
cuid: clg80x01c01ftpxnv8u667xn2
slug: how-do-you-create-and-use-interfaces-in-go

---

Interfaces are declared using the keyword interface. An interface type is defined as a set of methods. A variable of interface type can store any value that implements those methods.

interface MyInterface {
    // Methods go here
}

func main() {
    var myVar MyInterface
    // myVar can now store any value that implements MyInterface
}