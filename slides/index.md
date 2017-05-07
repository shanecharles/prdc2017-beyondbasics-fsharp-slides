- title : Beyond the Basics with F#
- description : Introduction to F# with some bonus
- author : Shane Charles
- theme : night
- transition : default

***

### Beyond the Basics with F#

![F#](images/fsharp256.png)

***

### Who am I?

- Shane Charles
- Developer @ Custom Software Solutions Inc.
- Functional programming enthusiast


    type ContactType = | Email | Twitter | Blog | GitHub

    let getContactInfo = function
      | Twitter -> "@dead_stroke"
      | Blog    -> "http://geekeh.com"
      | GitHub  -> "shanecharles"
      | Email   -> "shane_charles@outlook.com"

***

### What this talk is about

- What is F#
- Basic types
- Patterns
- Linq'ish?
- Async
- Agents
- Interop
- Extra resources

***

### What is F#

- General purpose programming langauge on .Net
- Member of the ML family
- Began as a research project out of Microsoft
 
***

### Defining a function


    let printName name = printfn "Hello %s" name

---

### Data types

#### Discriminated Union


    type Cattitude =
        | Lazy
        | Grumpy
        | Sarcastic
        | Indifferent


#### Record 


    type Cat = { name : string; mood : Cattitude }

---

### F# is all Class


    type Cat (name : string, mood : Cattitude) =
        let mutable mood = mood
        member x.Name = name
        member x.Mood 
            with get() = mood
            and set(value) = mood <- value

        override x.ToString() =
            sprintf "%s is %A" x.Name x.Mood

***

### Extra Resources

- F# for Fun and Profit (https://fsharpforfunandprofit.com)
- Microsoft Project Springfield (http://bit.ly/2jVeDpW)
- Winnipeg .Net Slack


    type ContactType = | Email | Twitter | Blog | GitHub

    let getContactInfo = function
      | Twitter -> "@dead_stroke"
      | Blog    -> "http://geekeh.com"
      | GitHub  -> "shanecharles"
      | Email   -> "shane_charles@outlook.com"

***
