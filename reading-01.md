// Quantity Trumps Quality //

- why? learning from our mistakes has tremendous value while theorizing over something can only go so far
- trying over and over again to improve
- "If you aren't building, you aren't learning.  Rather than agonizing over whether you're building the right thing, just build it!" 
    - this is what I try to keep in mind rather than seizing-up and worrying about failing

// Clean Code: Ch1 //
- transforming bad code into good code
- code needs to be written in a way machines can understand it
- clean code = cost-effective
    - takes less time overall
    - important to start with good code so it remains manageable as new features are added
    - wasting time 'wading' through bad code/senseless code as-in trying to make sense of it
    - "later equals never" - the intention of going back later to clean it up, this never actually happens
- messy code slows others down
    - if it's not clear how it works, when one goes to add or modify something it may result in other code breaking
    - as the mess increases and is added to, productivity decreases...and as pressure to increase productivity increases, the mess increases while productivity continues to decline further = a cycle that can not be broken out of
    - all devs feel the pressure to make a mess to get things done quickly and meet deadlines
    - however, it you keep it clean from the beginning, it will ulitmately be easier to meet those deadlines because the code is streamlined, efficient, and un-clouded
- 'code-sense' - one who can look at messy code and know what variations are possible and choose the best option 
    - straight-forward logic = nowhere for bugs to hide
    - minimal dependencies = easy to maintain
    - efficient = so it doesn't need altering 
        - simple and direct; decisive/focused
        - principle of single responsability vs muddled intent
        - broken windows analogy: no one cares => I stop caring => I start breaking windows
        - readability so easy for others to enhance it
        - TDD = cleanliness & no duplication
- we are "authors" = others will read our code; we are responsable for communcating to our audience effectively
- keep it clean over tine => will keep it from "rotting"
- I enjoyed this reading so I bought the book

// TDD: Red, Green, Refactor //

- an approach to build a test suite, write implementation code & optimize the codebase
- tests drive the design and development of software
- tdd = confirms code is working as expected
- cycle = compartamentalizes focus & saves tie while trying to implement a more robust solution
    - red = starting point; think about WHAT want to develop
        - write a test to add a feature; tests pass when a ddefined expectation is met
        - errors inform your approach
    - green = how to make test pass; the solution
        - once the test passes you can then seek ow to optimize the code
    - refactor = how to improve existing implementation so it's more efficient, no dups, more descriptive
        - use tests to stay on track

// Cycles of TDD //
- 3 laws of tdd:
    1. write a failingg test before any code
        - make it work before trying to clean it up; refactor as you go
    1. only write so mucha as needed to fail
        - as tests increase in specificity, increase the generality of the code
    1. write no more production code than it takes to pass
        - take a step back to ensure clean architecture

