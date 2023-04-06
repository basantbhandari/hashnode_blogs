---
title: "What is a parameterized pipe?"
datePublished: Thu Apr 06 2023 15:32:14 GMT+0000 (Coordinated Universal Time)
cuid: clg5a0y3a000609lbd5yedlj0
slug: what-is-a-parameterized-pipe
tags: parameterized-pipe

---

In Angular, a parameterized pipe is a type of pipe that accepts input parameters. Pipes are used to transform data in Angular applications, and they can accept arguments to modify their behavior.

With a parameterized pipe, you can pass additional parameters to the pipe to modify its behavior. These parameters can be used to customize the output of the pipe based on the input data or any other logic that you want to apply.

For example, let's say you have a custom pipe that formats dates. You could make this pipe parameterized by allowing the user to pass in a format string that defines how the date should be displayed. Here is an example of what the code might look like:

```typescript
import { Pipe, PipeTransform } from '@angular/core';
import { DatePipe } from '@angular/common';

@Pipe({
  name: 'customDate'
})
export class CustomDatePipe implements PipeTransform {
  transform(value: Date, format: string): string {
    const datePipe = new DatePipe('en-US');
    return datePipe.transform(value, format);
  }
}
```

In the code above, the `CustomDatePipe` is a custom pipe that takes a `Date` object and a `format` string as input. It then uses the built-in `DatePipe` from Angular to format the date according to the specified format.

You can use this pipe in your Angular templates like this:

```typescript
<p>{{ myDate | customDate:'MM/dd/yyyy' }}</p>
```

In this example, the `myDate` variable is piped through the `customDate` pipe, which formats the date using the `MM/dd/yyyy` format string.