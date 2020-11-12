---
layout: post
title:  "Comparing Go & Python"
date:   2020-11-12
categories: recurse center, go, python, scraping
---

## Comparing Go & Python

I've worked mostly in Python for a few years, and it feels like second nature to me. Learning Go this week has forced me to think about some of the major tradeoffs of Python that I've taken for granted.

### Creating arrays / maps / structs

Python:
```python
my_array = [1, 2, 3]
my_map = {"key1": 1, "key2": 2}
```

Go:
```golang
myArray := []int{1, 2, 3}
myMap := map[string]int{
    "key1": 1,
    "key2": 2    
}
```

Right away, it was obvious: Go needs more code, and I find the syntax less readable.

On the one hand, it takes me longer to write each line. On the other, it forces me to think about each line, and to make explicit choices about what types each variable will accept.

Like TDD, I found this difficult to start, but enabled much faster iteration as I made progress, and ultimately led to far fewer mistakes than I'm used to. I think this is a worthwhile tradeoff for Go!

### Checking if an element is in an array

```python
my_array = [1, 2, 3]
print(1 in my_array)  # True
```

```golang
myArray := []int{1, 2, 3}
/// how do I check if 1 is in myArray???
```

I learned, from [this post](https://stackoverflow.com/questions/10485743/contains-method-for-a-slice), that Go doesn't have the "contains" operation for an array, but it suggests "such a method is trivial to write". (!)

(along with "just", "only", "simple" — "trivial" is one of those words I find difficult in programming. To me, it implies that if I thought about it hard enough, I'll figure it out! In this case, though, I found it even more frustrating; I like the convenience of a method that someone else wrote, and I don't think that makes me a worse programmer!)

Turns out, this is how you do it:
```golang
// write your own `contains` function
myArray := []int{1, 2, 3}
func contains(s []int, e int) bool {
    for _, a := range s {
        if a == e {
            return true
        }
    }
    return false
}
fmt.Println(contains(myArray, 1))  // true
```

Or, you can use a map:
```golang
myMap := map[int]struct{}{1, 2, 3}
value, ok := myMap[1]
fmt.Println(ok)  // true
```

I understand the decision to make Go as small and simple as possible — it's a tradeoff between being useful enough, and having too many features — but I'll admit that I like the convenience of these kinds of Python features, and I'm glad they made the decision to include these kinds of features.

### Concurrency

One goal this week was to learn the basics of concurrency in Go. I've worked with concurrency in Python a few times, but know that it's considered to be fairly difficult compared to other languages, including Go.

I started with a small program — scrape multiple movies from a list of movies on https://letterboxd.com/ — and aimed to do the scraping concurrently. 

In the past, with this kind of system, I've worked with a queueing architecture, with multiple consumers and producers for one shared jobs queue. Something like:

```python
def delay_job(queue, job):
    queue.delay(job)  # sends to a queueing backend, e.g., AWS SQS


def process_job(queue):
    job = queue.get()  # receives job from a queueing backend
    process(job)
```

This has worked well, but is more work: you have to manage a queueing backend.

But I've found, in Python, this pattern is easier than writing a concurrent program. Here's a small example (Python >3.7) that prints out the numbers 0 to 99 concurrently, in a random order:
```python
import asyncio
import time
import random


async def process(job):
    await asyncio.sleep(random.randint(0, 1) / 10.0)  # sleep for a random number of milliseconds
    print(job)


async def enqueue_jobs(jobs):
    tasks = []
    for job in jobs:
        task = asyncio.create_task(process(job))  # create a coroutine for each job
        tasks.append(task)
    await asyncio.gather(*tasks)  # wait for all the tasks to finish


def main():
    jobs = range(100)
    asyncio.run(enqueue_jobs(jobs))  # run the loop
```
Aside from being fairly new (many of the async features of Python are still maturing), it's difficult for me to read and think about.

With Go, it's slightly easier and, I found, more readable:
```golang
func process(wg *sync.WaitGroup, i int) {
    defer wg.Done()  // signal that the job is done, decrementing the counter (`defer` will run this line after everything else in `process`)
    time.Sleep(time.Duration(rand.Intn(1) / 10.0))  // sleep for a random number of milliseconds
    fmt.Println(i)
}

func main() {
    var wg sync.WaitGroup  // declare a group of tasks to wait for; similar to what asyncio.gather provides
    for i := 0; i < 100; i++ {
        wg.Add(1)  // count the number of tasks
        go process(&wg, i)  // run this function as a "goroutine" (concurrently)
    }
    wg.Wait()  // wait for the entire group to finish
}
```

I don't have an example of this in Python, but I learned that managing goroutine communication is done in _channels_:

```golang
func process(i int, jobsChan chan int) {
    time.Sleep(time.Duration(rand.Intn(2 ) / 10.0) * time.Second)  // sleep for a random number of milliseconds
    jobsChan <- i
}

func main() {
    jobsChan := make(chan int)
    for i := 0; i < 100; i++ {
        go process(i, jobsChan)
    }
    for i := 0; i < 100; i++ {
        fmt.Println(<-jobsChan)
    }
}
```

I wrote my small scraper program to use goroutines and channels, and found it easier and faster than writing the same code in Python (once I got the hang of including types everywhere).

So far, I've found that Go has an initial learning curve — especially for common Python features I've taken for granted — but the static typing and strict compiler have enabled me to iterate much faster and make fewer mistakes, even without writing any tests. I hope I can take some of that learning back to developing in Python!
