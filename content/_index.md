+++
title = "JaKtA"
outputs = ["Reveal"]

+++

# JaKtA: <br> BDI agent-oriented programming <br> in pure Kotlin

<br>


Martina Baiardi <br />
m.baiardi@unibo.it <br /><br />

<small>Department of Computer Science and Engineering (DISI)<br>
Alma Mater Studiorum — Università di Bologna <br>
Via dell’Università 50, 47522 Cesena (FC), Italy </small>

---

## Distributed Applications
#### Running on unknown network topologies

<br/>


{{< figure src="images/path2.svg" width="50%" >}}

---

#### May be subject to unpredictable connectivity failures

<br />

{{< figure src="images/path2-6.svg" width="50%" >}}

---

#### We need *autonomous* entities <br/>capable to *adapt* their behaviour to the failure <br/>and continue to work as expected 
<br />

{{< figure src="images/path2-6-1.svg" width="50%" >}}

---

#### Autonomous entity == *Agent*

<br />

{{< figure src="images/path43-7.svg" width="50%" >}}

---

# Agent-Oriented Programming

<br />


{{< figure src="images/rect46.svg" width="50%" >}}

<small>[1] Weiss, Gerhard, Multiagent Systems. MIT Press, 2013</small>

---

# Agent-Oriented Programming

<br />

{{< figure src="images/rect46-1.svg" width="50%" >}}

<small>[1] Weiss, Gerhard, Multiagent Systems. MIT Press, 2013</small>

---

# BDI Agents [2]
#### Beliefs, Desires, Intentions

<br />

Agents are autonomous entities modeled through three main abstractions:
- *Beliefs*: mental state of the agent, that changes over time.
- *Desires*: motivational state of the system.
- *Intentions*: deliberative state of the agent.

<div>
<br />
<small style="text-align: left"> 
[1] Bratman, Michael. "Intention, plans, and practical reason." (1987) <br />
[2] Anand S. Rao and Michael P. Georgeff. "BDI agents: From theory to practice." (1995) <br />
[3] Anand S. Rao. "Agentspeak(l): BDI agents speak out in a logical computable language." (1996) 
</small>
</div>

---

# BDI Agents [2]


{{< figure src="images/Interpreting-AgentSpeakL-Programs.png" width="50%" >}}

<div>
<small style="text-align: left"> 
[1] Bratman, Michael. "Intention, plans, and practical reason." (1987) <br />
[2] Anand S. Rao and Michael P. Georgeff. "BDI agents: From theory to practice." (1995) <br />
[3] Anand S. Rao. "Agentspeak(l): BDI agents speak out in a logical computable language." (1996) 
</small>
</div>

---

# BDI Agent Programming Languages

<br />

{{< figure src="images/AOPlang.svg" width="50%" >}}

<br />

<div>
<small style="text-align: left"> 
[1] Collier, R.W., Russell, S.E., Lillis, D.. "Reflecting on agent programming with AgentSpeak(L). I" (2015) <br />
[2] Hindriks, K.V.. "Programming rational agents in GOAL." (2009) <br />
[3] Pokahr, A., Braubach, L., Lamersdorf, W.. "Jadex: A BDI reasoning engine." (2005) <br />
[4] Bordini, R.H., Hübner, J.F., Wooldridge, M.J.. "Programming Multi-Agent Systems in AgentSpeak using Jason." (2007) <br />
[5] D’Urso, F., Longo, C.F., Santoro, C.. "Programming intelligent iot systems with a python-based declarative tool." (2019) <br />
[6] Palanca, J., Rincon, J.A., Carrascosa, C., Julián, V., Terrasa, A.. "A flexible agent architecture in SPADE." (2022)
</small>
</div>

---

<!-- ## Current trend: multi-paradigm languages
<br>

Several languages include more than one paradigm:

| Language | Object-Oriented | Functional |
| :---:  | :---: | :---: |
| Java  | {{< tick >}} {{< /tick >}} | {{< maybe >}} (Java 8){{< /maybe >}} |
| C#    | {{< tick >}} {{< /tick >}} | {{< maybe >}} {{< /maybe >}} |
| Scala | {{< tick >}} {{< /tick >}} | {{< tick >}} {{< /tick >}} |
| Kotlin| {{< tick >}} {{< /tick >}} | {{< tick >}} {{< /tick >}} |
| Ruby  | {{< tick >}} {{< /tick >}} | {{< maybe >}} {{< /maybe >}} |
| Caml | {{< maybe >}} (OCaml) {{< /maybe >}} | {{< tick >}} {{< /tick >}} |
| Python | {{< tick >}} {{< /tick >}} | {{< maybe >}} {{< /maybe >}} |
| JavaScript| {{< maybe >}} {{< /maybe >}} | {{< maybe >}} {{< /maybe >}} |

---

However, Agent-Orientation / BDI is never considered

| Language | Object-Oriented | Functional | Agent-Oriented
| :---:  | :---: | :---: | :---: |
| Java  | {{< tick >}} {{< /tick >}} | {{< maybe >}} (Java 8){{< /maybe >}} | {{< cross >}} {{< /cross >}} |
| C#    | {{< tick >}} {{< /tick >}} | {{< maybe >}} {{< /maybe >}} | {{< cross >}} {{< /cross >}} |
| Scala | {{< tick >}} {{< /tick >}} | {{< tick >}} {{< /tick >}} | {{< cross >}} {{< /cross >}} |
| Kotlin| {{< tick >}} {{< /tick >}} | {{< tick >}} {{< /tick >}} | {{< cross >}} {{< /cross >}} |
| Ruby  | {{< tick >}} {{< /tick >}} | {{< tick >}} {{< /tick >}} | {{< cross >}} {{< /cross >}} |
| Caml | {{< tick >}} (OCaml) {{< /tick >}} | {{< tick >}} {{< /tick >}} | {{< cross >}} {{< /cross >}} |
| Python | {{< tick >}} {{< /tick >}} | {{< maybe >}} {{< /maybe >}} | {{< cross >}} {{< /cross >}} |
| JavaScript| {{< maybe >}} {{< /maybe >}} | {{< maybe >}} {{< /maybe >}} | {{< cross >}} {{< /cross >}} |

---

#### No *active* proposals for including *AOP/BDI abstractions* into mainstream languages
<br>

# WHY?

---

# BDI Libraries

<br>
<br>

{{% multicol %}} {{< col class="col-75">}}

* Built for mainstream languages
* Subject to the **syntactic restrictions** of their host language
  * "True" AOP/BDI feeling hardly achieved

{{< /col >}}

{{< col class="col-25">}}

{{< fragment >}}
## <i class="fa-solid fa-arrow-right"></i> **custom language**
{{< /fragment >}}

{{< /col >}} {{% /multicol %}}

---

# AOP Custom Languages
* <span class="green">Great ergonomy for BDI AOP (made by purpose) </span>
* <span class="red">BDI-specific, not multi-paradigm </span>
* <span class="red">Steep learning curve</span>
* <span class="red">Require custom tooling (IDEs, code suggestions, syntax highlighters, linters...)</span>
* <span class="red">Small community</span>
* <span class="red">High maintenance cost!</span>

---

# A hybrid approach

<!-- ![](images/ergonomy.png) -->

<!-- {{< figure src="images/ergonomy.png" width="60%" >}}  -->

## We searched for popular BDI AOP languages

* **PYPL** PopularitY of Programming Language [<i class="fa-solid fa-arrow-up-right-from-square fa-xs"></i>](https://pypl.github.io/PYPL.html)

* **TIOBE** [<i class="fa-solid fa-arrow-up-right-from-square fa-xs"></i>](https://www.tiobe.com/tiobe-index/)

* **Stackoverflow developer survey** [<i class="fa-solid fa-arrow-up-right-from-square fa-xs"></i>](https://survey.stackoverflow.co/2023/#most-popular-technologies-language-prof)

<br>
<br>
<br>

{{% fragment %}}

# No one <i class="fa-regular fa-face-frown"></i>

{{% /fragment %}}

---

# Why?

We identified 4 possible reasons

---

## 1. Learning curve vs ergonomics
<br>
<br>

{{< multicol class="text-center" >}}{{< col class="col-6" >}}

<h4> Libraries </h4>
<br>

<div>
<i class="fa-solid fa-check" style="color: green;"></i>
Gentle learning curve
</div>

<div>
<i class="fa-solid fa-check" style="color: green;"></i>
Large community
</div>

<div>
<i class="fa-solid fa-xmark" style="color: red;"></i>
Poor ergonomicity
</div>

{{< /col >}}{{< col class="col-6" >}}

<h4> Custom Languages </h4>
<br>

{{< tick >}}
High ergonomicity
{{< /tick >}}

{{< cross >}}
Steep learning curve
{{< /cross >}}

<div>
<i class="fa-solid fa-xmark" style="color: red;"></i>
Small community
</div>

{{< /col >}}{{< /multicol >}}

---

## 2. Tooling
#### (IDE, code suggestion, syntax highlighter, ...)
<br>
<br>

{{% multicol class="text-center" %}}{{% col %}}

<h4> Libraries </h4>
<br>

* Rely on existing **development tools**
* Can be integrated with existing **libraries**

{{% /col %}}{{% col %}}

<h4> Custom Languages </h4>
<br>

* Require **novel tooling**
    * and related **maintenance**
* Require **novel libraries** or **explicit bridges** to other ecosystems

{{< /col >}}{{< /multicol >}}

---

## 3. Middleware/Runtime requirements
<br>

* BDI AOP libraries rely on specific runtimes
    * e.g. **JVM**, **Python interpreter**, ...

* But systems could be designed to run on a large variety of devices, 
    * from **web** to **wearable**-oriented applications 

---

## 4. Concurrency model
<br>

* Limited configuration over the system **execution**
    * impact the system design
* BDI model definition should be completely agnostic<br>of the underlying concurrency model
    * Which should be **pluggable**.

---

# JaKtA: <br> <u>Ja</u>son-like <u>K</u>o<u>t</u>lin <u>A</u>gents

Internal Domain-Specific Language (DSL) implemented in Kotlin

* Multi-paradigm support: OOP + FP + BDI AOP
* Hosted on a mainstream language: gentle learning curve
  * Great learning resources for Kotlin
  * Significantly large community for help
* Reuses the entire existing Kotlin toolchain
  * Developed and *maintained* by the language maintainers and the community
  * Maintenance is greatly reduced
* Good ergonomy

---

# Why kotlin?
<br>

{{% multicol %}}{{% col %}}
* Natively multi-paradigm (OOP + FP)
* Statically typed
  * With a good IDE, helps understanding what can be written where
* Direct support to internal DSLs
  * a.k.a "Type-safe builders" in the Kotlin documentation
* Support for multiplatform development
{{% /col %}}

{{< col class="text-center">}}

* Growing community
  * Strongly pushed by Google for Android
{{< figure src="images/android-kotlin.png" width="70%" >}}

{{% /col %}}{{% /multicol %}}


---
# Jakta architecture

{{< figure src="images/jacop_modules.svg" width="50%" >}}

---

## Jakta: multi-paradigm AOP/BDI+OOP+FP


```kotlin
mas {                                                   // BDI specification
  fun allPlayers(team: String) =
    Regex("""<a\s(\X*?)\sdata-cy="player">(.*)<\/a>""") // Object-oriented regex library
        .findAll(URL("https://www.besoccer.com/team/squad/$team").readText())
        .map { team to it.groupValues[2] }              // Lambda expression (Functional style)

  listOf("napoli", "milan", "internazionale")           // Kotlin standard library
      .flatMap(::allPlayers)                            // Higher-order function (Functional style)
      .forEach { (team, player) ->                      // Destructuring declaration
          agent(player) {
              beliefs { fact { squad(team) } }
              goals { achieve(start) }
              plans {
                  +achieve(start) onlyIf { squad(S).fromSelf } then {
                      execute(print("Hello! I play for", S))
                  }
              }
          }
      }
}.start()
```

<i class="fa-solid fa-file-code"></i> [SoccerMas.kt](https://github.com/jakta-bdi/jakta-examples/blob/main/src/main/kotlin/it/unibo/jakta/agents/examples/soccer/SoccerMas.kt)

---

# JakTa
<br>

(currently) JVM based with native Android support, mobile-ready

{{< figure src="images/android-tictactoe.png" width="50%" >}}


<i class="fa-solid fa-file-code"></i> [TicTacToeMas.kt](https://github.com/jakta-bdi/jakta-examples/blob/main/src/main/kotlin/it/unibo/jakta/agents/examples/tris/TicTacToeMas.kt)

<i class="fa-brands fa-android"></i> [Android Project](https://github.com/jakta-bdi/jakta-android-example)

---

# Future work

* {{% multicol %}}{{% col class="col-4" %}}
**Multiplatform targeting**
{{% /col %}}{{% col class="col-8"%}}
{{< figure src="images/jakta-mp.png" >}}
{{% /col %}}{{% /multicol %}}
* **Pluggable concurrency model**, neatly searating BDI definitions and the underlying threading
* **Improved DSL syntax** to further improve the multi-paradigm integration (AOP/BDI + OOP + FP)

---

# try jakta
<br>

[github.com/jakta-bdi/jakta-examples](https://github.com/jakta-bdi/jakta-examples)

{{< figure src="images/qr-code.svg" width="20%" >}}
