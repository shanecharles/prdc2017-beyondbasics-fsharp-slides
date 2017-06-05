- title : Beyond the Basics with F#
- description : Introduction to F# with some bonus
- author : Shane Charles
- theme : night
- transition : default

***

### Beyond the Basics with F#

![F#](images/fsharp256.png)

***

### Thank the Sponsors

![Sponsors](images/sponsors.png)

***

### About me

- Shane Charles
- Burning Ice Solutions Inc.
- Functional programming enthusiast
- Board member for Winnipeg .Net UG


    type ContactType = | Email | Twitter | Blog | GitHub

    let getContactInfo = function
      | Twitter -> "@dead_stroke"
      | Blog    -> "http://geekeh.com"
      | GitHub  -> "shanecharles"
      | Email   -> "shanecharles@burningicesolutions.com"

***

### What this talk is about

- What is F#
- Basics
- REPL
- Summary

***

### What is F#

- General purpose programming langauge on .Net
- Member of the ML family
 
***

### Functional First

- Immutable by default
- Discourages the use of nulls
- You can still do OOP

---

### Discriminated Union

- Value can be one or the other
- Think enums with attached data


    type Cattitude =
        | Grumpy of multiplier : uint32
        | Sarcastic of evidence : string list
        | Indifferent
        | Affectionate
        | Exploding

---

### Record 

- Data structure with named values
- Structural equality by default


    type Cat = { name : string; mood : Cattitude }

---

### F# is all Class


    [<AllowNullLiteral>]
    type Cat (name : string, mood : Cattitude) =
        let mutable mood = mood
        member x.Name = name
        member x.Mood 
            with get() = mood
            and set(value) = mood <- value

        override x.ToString() =
            sprintf "%s is %A" x.Name x.Mood

---

### Linq'ish


    Seq.map     // Select
    Seq.filter  // Where
    Seq.sortBy  // OrderBy
    Seq.choose  // Where + Select
    Seq.fold    // Aggregate
    Seq.unfold  // ¯\_(ツ)_/¯ 

***

### REPL Time

*** 

### Summary

- Rapid prototyping with REPL and FSX files
- Combine active patterns to improve readability
- Async workflow with bang notation
- Create our own computation expressions / builders
- Rail Road Oriented Programming

***

### Extra Resources

- F# for Fun and Profit (https://fsharpforfunandprofit.com)
- Winnipeg .Net Slack (http://winnipegdotnet.org)


    type ContactType = | Email | Twitter | Blog | GitHub

    let getContactInfo = function
      | Twitter -> "@dead_stroke"
      | Blog    -> "http://geekeh.com"
      | GitHub  -> "shanecharles"
      | Email   -> "shanecharles@burningicesolutions.com"

***
