---
layout: post
title: "Keep calm in Go - panic, defer and recover"
description: ""
category:
tags:
  - golang
---

Normally you work with "exceptions" in golang by simply returning `error` from function
and then checking it in `if` statement when calling it. But sometimes
traditional *"try ... catch ... finally"* may be more convenient. It can be
achieved using golang's `panic`, `defer` and `recover`.

Here is example of `try ... catch ... finally` in Go:


{% highlight go %}

import "fmt"

func main(){
  // finally
  defer func(){
    fmt.Println("FINALIZATION")
  }()

  // catch
  defer func(){
    if exception := recover(); exception != nil {
      fmt.Printf("`Exception` catched: %v\n", exception)
    }
  }()

  // try
  x := make([]int, 1)
  fmt.Println(x[35]) // this line will panic (e.g. throw exception):
                     // "index out of range"
}

{% endhighlight %}

You can panic with your custom exceptions of any type. Then you just check type
of recovered panic using typeswitch or reflect package...

As proof of concept (and for fun) I created [Calmly
package](https://github.com/JosephBuchma/calmly)
