---
title: The Hamler Programming Language
---

# The Hamler Programming Language

**Hamler** is a strongly-typed language with compile-time typechecking and built-in support for concurrency and distribution.

**Hamler** empowers industries to build the next generation of scalable, reliable, realtime applications, especially for 5G, IoT and edge computing.

## **Why Hamler?**

For almost a decade, we have been developing software systems based on Erlang/OTP, especially our main product [EMQ X](https://github.com/emqx/emqx) - the scalable open-source MQTT broker. So, we have always believed that Erlang is a masterpiece of engineering. With amazing concurrency, distribution and fault tolerance, it is one of the few general-purpose language platforms able to properly handle concurrency and soft realtime.

However, from all the experience writing Erlang, we believe that the following features can help Erlang programmer better adapt to the coming wave of 5G, IoT and edge-programming and attract more people for using BEAM.

- Compile-time type checking and type reference
- ADTs, Function Composition, Type Classes
- More friendly syntax for prosperous communities
- Functor, Applicative and Monad...:)

Now all the features are avaliable in the Hamler programming language.

## **Features**

- Functional programming
- Haskell and ML style
- ADT and Type Checking/Inference
- Functions, higher-order functions
- Currying and partial application
- Pattern matching, and Guards
- List comprehension
- Applicative and Monad
- Advanced module system
- Built-in concurrency

## **Design**

The Hamler source code is parsed to generate CST, then CoreErlang's IR is generated after CST -> AST -> CoreFn's syntax tree transformation, syntax analysis and type checking. The code is then used by the Erlang compiler to generate the final Beam bytecode.

The Hamler compiler architecture is shown below:

![hamler-compiler](images/compiler.png)

The Hamler 0.1 compiler was initially attempted to be implemented based on the GHC 8.10.1, but was later changed to adapt from Purescript Compiler 0.13.6's implementation.

## **Installation**

```shell
brew install hamler
```

## **Try the interpreter**

```shell
hamler repl

> -- List, range and enums
> [1,2,3]
> [1..10]
> ['a'..'z']

> import Data.Map as Map
> -- New map
> m = #{"foo" => "bar", "bar" => "foo"}
> -- Match Map
> #{"foo" := a, "bar" := b} = m
> -- get, put
> Map.get "foo" m -- a = "bar"
> Map.get "bar" m -- b = "foo"
> m1 = Map.put "key" "val"
> -- keys, values
> keys = Map.keys m
> values = Map.values m
```

## **Create a project**

```shell
mkdir demo-project
cd demo-project
hamler init
make
make run
```

### **Documentation**

- [Cheatsheet][Cheatsheet]
- [Why Hamler?][WhyHamler]
- [Quick Start][QuickStart]
- [Basic Data Types][BasicDataTypes]
- [Pattern Matching][PatternMatching]
- [Recursions][Recursions]
- [Type Classes][TypeClasses]
- [Applicative, Monad][ApplicativeMonad]
- [Foreign Language Interface][FFI]
- [Concurrent and Distribution][ConcurrentAndDistribution]

## **Community, discussion and supports**

You can reach the **Hamler** community and core team via the following channels:

- [Slack - emqx/hamler-lang](https://slack-invite.emqx.io/)
- [Twitter - @hamlerlang](https://twitter.com/hamlerlang)
- [Reddit - /r/HamlerLang](https://www.reddit.com/r/HamlerLang/)
- [Medium - @hamlerlang](https://medium.com/@hamlerlang)

## **Contributing**

To contribute to **Hamler** project:

- Report issues : submit any bugs, issues to [hamler/issues][hamler-issues]
- Contribute code: Fork the project, and submit feature requests to [hamler-lang/hamler][hamler-project]
- Submit a proposal: Fork the [hamler-wiki][hamler-wiki] project and submit pull request

### [**Core Team**]

The **Hamler** core team comes from [EMQ Technologies Co., Ltd.](https://emqx.io/) now.

- [Feng Lee](https://github.com/emqplus): The designer of Hamler language. Came up with the vision and implemented most of the libs
- [Yang M](https://github.com/EMQ-YangM): Implemented Hamler Compiler
- [S Hu](https://github.com/SjWho): Maintainer of the documentations
- [Shawn](https://github.com/terry-xiaoyu): Contributed [rebar3_hamler][rebar3_hamler] plugin
- [Rory Z](https://github.com/zhanghongtong): Contributed [homebrew][homebrew] install package
- [wivwiv](https://github.com/wivwiv): Designer of hamler-lang.org website
- [CrazyWisdom](https://github.com/CrazyWisdom): maintainer of hamler-lang.org
- [ysfscream](https://github.com/ysfscream): maintainer of hamler-lang.org
- [juan6666](https://github.com/juan6666)：designer of Hamler language logo

## **About EMQ**

[**EMQ**](https://www.emqx.io/en/) is an open source software company providing highly-scalable, real-time messaging and streaming platform for IoT applications in 5G Era.

## **License**

BSD3

[Cheatsheet]: https://github.com/hamler-lang/documentation/blob/master/Cheatsheet.md
[WhyHamler]: https://github.com/hamler-lang/documentation/blob/master/guides/01_WhyHamler.md
[QuickStart]: https://github.com/hamler-lang/documentation/blob/master/guides/02_QuickStart.md
[BasicDataTypes]: https://github.com/hamler-lang/documentation/blob/master/guides/03_BasicTypesFucntionsAndOperators.md
[PatternMatching]: https://github.com/hamler-lang/documentation/blob/master/guides/04_MoreTypesandPatternMatching.md
[Recursions]: https://github.com/hamler-lang/documentation/blob/master/guides/05_HigherOrderFunctionsAndRecursions.md
[TypeClasses]: https://github.com/hamler-lang/documentation/blob/master/guides/06_TypeClasses.md
[ApplicativeMonad]: https://github.com/hamler-lang/documentation/blob/master/guides/07_ApplicativeAndMonad.md
[FFI]: https://github.com/hamler-lang/documentation/blob/master/guides/ForeignLanguageInterface.md
[ConcurrentAndDistribution]: https://github.com/hamler-lang/documentation/blob/master/guides/ConcurrentAndDistribution.md
[rebar3_hamler]: https://github.com/hamler-lang/rebar3_hamler
[homebrew]: https://github.com/hamler-lang/homebrew-hamler
[hamler-issues]: https://github.com/hamler-lang/hamler/issues
[hamler-project]: https://github.com/hamler-lang/hamler
[hamler-wiki]: https://github.com/hamler-lang/hamler-wiki

