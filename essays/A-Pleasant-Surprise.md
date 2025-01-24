---
layout: essay
type: essay
title: "A Pleasant Surprise"
date: 2025-01-23
published: true
labels:
  - Typescript
  - Athletic Software Engineering
---

<img width="200px" class="rounded float-start pe-4" src="../img/typescriptlogo.png">

## First impressions

My initial thoughts on Typescript were that it would potentially be difficult to learn or that it would take an immense amount of time, just like the experience of learning C had been. However, now that I have started learning it, I have found none of that to be accurate, or at least as true. While it has its new concepts and style, it is nowhere near as daunting as C and C++. The automatic memory management luxury that Typescript has was a bonus, especially compared to having to learn manual memory handling previously. Learning Typescript is much more similar to my experience learning Java with all the built-in methods, though its type system and syntax required a slight adjustment in thinking methods.

## Typescipt success story?

Past my initial perspective and after diving into the world of Typescript, I have formed some personal opinions about the programming language. I was pleasantly surprised at Typescript's versatility, making it very appealing for multifunctional purposes and easing the burden on the coder. Even further on its versatility, Typescript has flexibility. For example, it can catch errors at compile time instead of runtime, which is a significant advantage, improving code reliability and maintainability. While I would say I need a bit more time to truly be comfortable with this new language, it is definitely a lot more digestible than I previously conceived.

## Preparing for the future

Putting my new Typescript skills into practice with athletic software engineering, particularly with Workout of the Day exercises in my ICS 314 class, has been both challenging and engaging. These timed coding practices push me to think quickly and analytically to solve the problems presented to me under pressure.  I enjoy the puzzle-like structure they provide while also helping me improve my knowledge of the programming language through hands-on practice and experience. These WODs are similar to the algorithmic problem-solving I do in my PANDA (Programming AND Algorithms) club, which stimulates job interview questions. So, not only am I growing my programming skills and knowledge through athletic software engineering but, I am also setting myself up for a successful future in the career space.

## WOD Example with Return type verstility in Typescript
One feature I found particularly useful in Typescript is union types (|), which allow functions to return different data types depending on the situation. Here is an example of my solution from a WOD exercise demonstrating this concept:

```typescript
function temperatureConverter(temperature: number, temperatureType: string): number | string{
    if (temperatureType == "F"){
        return (temperature - 32) * 5/9;        // returns a number
    } else if (temperatureType == "C"){
        return (temperature * 9/5) + 32;        // returns a number
    } else {
        return "Illegal temperature type";      // returns a string
    }
}
console.log(temperatureConverter(212, "F"));     // 100
console.log(temperatureConverter(0, "C"));       // 32
console.log(temperatureConverter(0, "X"));       // Illegal temperature type
```
