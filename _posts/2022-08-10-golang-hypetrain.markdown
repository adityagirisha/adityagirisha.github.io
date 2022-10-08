---
layout: post
title:  'The Golang Hypetrain, A Java Devs perspective'
description:
date:   2022-10-07 18:05:55 +0300
image:   '/images/golang.jpg'
tags:   [golang, java]
---


> To Go or not to Go...

Golang, or Go for short, is the relatively new kid in town. Its debut, however, has caused a wave of widespread adoption among companies and developers. 

A Stack Overflow survey, Golang took third place in the ranking of programming languages that developers would like to study.

So, as a Java developer who recently decided to learn Go, let's talk about how different it is from what we are used to...

> The Journey

As I started my journey, I immediately felt an uneasiness. I couldn't put my finger on it at first... The basic syntax looked fine and wasn't too far off from my experience in Java or Python. 

But it grew stronger as I studied the OOPS facilities, concurrency mechanics, and package imports. It felt weird, it felt off, it felt like it wasn't as verbose as I'd like a next generation language to be...

I slowly understood what kind of language Go wanted to be, but I couldn't put it into words until I came across the go proverbs ( [go-proverbs.github.io](https://go-proverbs.github.io/) ) and everything became as clear as day.


Golang, at its center, has one goal in mind : simplicity. It rejects anything that makes it feel complex. Clear is better than clever. And getting used to this paradigm has its fair share of difficulties.


> The Parts I liked

• You know the language was designed by logically thinking people when they decided to name int, long, float, and double as int32, int64, float32, and float64 repectively. 

• Want to include a dependecy? Just include the github repo and Golang will take care of the rest.

<pre style="background-color:#ebfbcc;width:100%;padding:3%;margin-top:5%;margin-bottom:5%" >
<code >
package main

import (
	"fmt"
	"github.com/spf13/cobra"
	"mymodule/mypackage"
)

func main() {
    fmt.Println("Hello World!")
}
</code>
</pre>

• The concurrency. OH. MY. GOD. The concurrency is unparalleled (pun intended). Want to run something on a thread? Just add go infront of the fucntion call. Want to communicate between threads? Channels to the rescue. Its a bit tricky at first but intuitive nonetheless.

<pre style="background-color:#ebfbcc;width:100%;padding:3%;margin-top:5%;margin-bottom:5%" >
<code >
package main

import (
    "fmt"
    "time"
)

func f(from string) {
    fmt.Println(string)
}

func main() {
    //normal call
    f("direct")
    //goroutine call
    go f("goroutine")
}
</code>
</pre>

• Last but not least. It's the language of the cloud. Fast compilation times. lightweight, good compatibility with large number of operating systems. 

It's no surprise that Docker, Kubernetes, and Terraform were all created in Golang. And they make deploying large-scale architectures a cakewalk with Golang.

> The Parts I didn't

• Java has an extensive list of collections... Golang? All you get is arrays, slices, and maps. Don't get me wrong here, there are dozens of third-party libraries that offer these collections. But the inbuilt ones leave us desiring for more.


• Java 8 has an astoundingly good functional programming support with lambda functions and stream APIs... Golang? Not so much. This is because Go does not want to have many different ways of doing the same task. As someone who lives and breathes in Java 8, it is a bit disheartening.


• Java, C, C++, and Python more or less have the same error handling... Golang? There is no concept of Exceptions. There is no try and catch block. It just returns the error values along with the result, and somewhere along the code the devs are expected to handle it gracefully. 

<pre style="background-color:#ebfbcc;width:100%;padding:3%;margin-top:5%;margin-bottom:5%" >
<code >
db, err := getDbConnection()
if err != nil {
  log.Fatal(err)
  return
}
defer db.Close()
data, err := ioutil.ReadFile("test.txt")
if err != nil {
    fmt.Println("File reading error", err)
    return
}
for _, line := range data.lines() { 
  stmt, err := db.Prepare("INSERT INTO users(name) VALUES(?)")
  if err != nil {
    log.Error(err)
    return
  }
  res, err := stmt.Exec(line)
  if err != nil {
    log.Error(err)
    return
  }
  lastId, err := res.LastInsertId()
  if err != nil {
    log.Error(err)
    return
  }
  rowCnt, err := res.RowsAffected()
  if err != nil {
    log.Error(err)
    return
  }
  log.Printf("ID = %d, affected = %d\n", lastId, rowCnt)
}
</code>
</pre>

This makes the code a bit stuffed with error management.

• There are other drawbacks like no generics support, bringing back pointers, and a lack of extensive libraries. However, it is nothing you can shake off.

> Conclusion?

Go is built for different things. It wasn't meant for competitive coding, or an API server, or for prototyping. It was meant to solve the web app development challenges. It was meant for building low-latency, high-performance servers with low-level protocol implementations. So, comparing it to Java is like comparing apples to oranges for now. But Go is young and I'm curious to see what kind of orange it will turn out to be.


So should you go for Go? It's not a bad skill to have. The world is moving to the cloud, and Golang is undoubtedly a key player, but it's not going to replace Java; it's designed for different purposes.You'll find yourself more productive as a API developer with Java and Spring Boot and prototyping/problem solving with Python.