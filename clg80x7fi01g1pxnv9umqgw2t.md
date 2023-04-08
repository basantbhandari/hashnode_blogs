---
title: "How do you use Go modules to manage dependencies?"
datePublished: Sat Apr 08 2023 13:40:42 GMT+0000 (Coordinated Universal Time)
cuid: clg80x7fi01g1pxnv9umqgw2t
slug: how-do-you-use-go-modules-to-manage-dependencies

---

To manage dependencies using Go modules, you need to first create a go.mod file in the root directory of your project. This file will contain the module name and the module dependencies. To add a dependency to your project, you can use the "require" directive. For example, to add the "fmt" package as a dependency, you would add the following to your go.mod file:

require (

fmt

)