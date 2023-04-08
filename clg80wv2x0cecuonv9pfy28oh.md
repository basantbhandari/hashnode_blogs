---
title: "How does Go handle garbage collection?"
datePublished: Sat Apr 08 2023 13:40:26 GMT+0000 (Coordinated Universal Time)
cuid: clg80wv2x0cecuonv9pfy28oh
slug: how-does-go-handle-garbage-collection

---

Go handles garbage collection through a process known as "tracing". When the Go runtime detects that there is no more references to an object, it will trace the object to determine if it is reachable. If the object is not reachable, the runtime will garbage collect the object.