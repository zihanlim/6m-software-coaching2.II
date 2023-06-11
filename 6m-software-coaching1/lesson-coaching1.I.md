Review
    a. SDLC and Scrum
    
    SDLC - Software Development life cycle
        Requirement Analysis - Gathering the business and technical requirements.
        Defining - Defining the functional and non-functional requirements.
        Designing - Translating the functional requirements into workable tasks.
        Coding - Writing code a.k.a. development phase.
        Testing - Ensuring the outcome of development aligns with the defined requirements.
            Functional tests - tests the functionality of the application
            Non functional tests - tests the other aspects of the application / service
        Deployment - Going live into production.
        Maintenance - Monitoring systems health and fix errors when arises.
    
    Scrum - Agile Methodology
        Sprint - Time boxed event for creating Product Increments
        Events
            Sprint Planning - select user stories for the current sprint and break them down into tasks
            Daily Scrum - short meeting within the team about tasks done, tasks to be done, as well as any blockers or hurdles
            Sprint Review - presentation of Product Increment to stakeholders and discussion
            Sprint Retrospective - discussion of practices within Sprint that would be stopped, started, or continued
        Artifacts
            Product Backlog - contains all user stories
            Sprint Backlog - contains user stories to be done in the current Sprint
            Product Increment - contains all work done leading up to the current Sprint based on the team's definition of done
        User Stories - a requirement for the application following the format:
            As a ___, I want to ___, so that ___

    b. CLI and Git commands
        CLI - command line interface (terminal or powershell)
            mkdir - makes a directory
            pwd - shows present working directory
            ls - lists items inside a directory
            cd - changes directory
                cd .. - moves up one level
                cd a/b/c - chaining
            touch / ni - creates a file

        Git - version control system
        Fork vs Clone
            fork - copies one remote repo to your remote repository
            clone - copies a remote repository to your local machine

            When accessing other people's remote repositories, we fork first, before cloning

        Commands:
            git clone <url> - clones the git repo into the directory
            git add . - adds all the modified files in the directory to a commit
            git commit -m "message" - commits the changes
            git remote -v - checks remote repositories linked to the local repository
            git push <remote alias> <branch to push> - pushes the changes into remote repository  
                ex. git push origin main

    c. HTML and CSS
        HTML - structure for the page
            Element example:
                <h1 id="intro">This is a page</h1>
            <h1></h1> - tags
                We also have self closing tags - <img src=""/>
            id="intro" - attribute and value
            This is a page - content

        Box model - everything is a box
            Block elements - div, h1 - take up the entire length of the screen
            Inline elements - input, span - take up the length of the content

            Q: What are padding, margin, and border?

        CSS - styling for page
            Styling example:
                #intro {
                    color: red;
                    font-weight: bold;
                }

                #intro - css seletor
                color - property
                red - value

            Question about CSS Selectors:
            1. How to target classes?
            2. What is the universal selector?
            3. What is specificity?

    d. JS
        i. Data types and variables
            data types  - string, number, boolean, undefined, null
            let - creates a variable
                ex: let x = 10; //value 10 is assigned to x
            const - creates a constant 
                ex: const dbName = "myDatabase"; //value can not be changed

        ii. Operators
            1. Arithmetic - mathematical operations (+, - , *, /, %)
                100 / 3 => 33.333
                100 % 3 => 1 //Remainder
            2. Comparison - compares two values (==, ===, >, <, >=, <=, !=)
                10 == 10 => true
                10 == "10" => true
                10 === "10" => false //Strict equality -> checks both the type and value
            3. Logical - compares two boolean statements (&&, ||, !)
                && (AND) - both statements should be true
                || (OR) - at least one statement should be true
                ! (NOT) - reverses the truth value

                let isDark = false;
                let isTall = true;
                let isHandsome = true;

                console.log(isDark && isTall); //false
                console.log(isDark || isHandsome); //true
                console.log(!isHandsome); //false

                console.log((!isDark || isHandsome) && isTall); //true

        iii. Control Flows
            1. if-else statements
                if(condition) {
                    statements to do if the condition is true                
                } else {
                    statements to do if the condition is false
                }

                Q: is the else block optional? yes

            1a. Ternary statements
                condition ? value when condition is true : value when condition is false
            2. switch-case
                switch(pattern to match) {
                    case value1:
                        statements to do if pattern matches value1
                        break;
                    case value2:
                        statements to do if pattern matches value2
                        break;
                    default:
                        statements to do if no matches are made 
                }
            3. while loop
                while (condition){
                    statements to do while condition is true
                    //Don't forget a statement such as an increment or decrement to eventually exit the loop
                }
            4. do while loop
                do {
                    statements to do while condition is true
                    //Don't forget a statement such as an increment or decrement to eventually exit the loop
                } while (condition)

                Main difference is that while checks first before running, do-while runs before checking

            5. for loop
                for(initial value; condition; increment/decrement){
                    statements to do while condition is true
                }

        iv. Arrays and Objects
            Arrays - collection of related values  
                ex. const beatlesMembers = ["John", "Paul", "George", "Ringo"];

                The index is the address of a specific element in the array
                ex. console.log(beatlesMembers[1]); //This should be Paul
                Note that the index of arrays start with 0.

                Loops can be used to read through the entire content of the array
                ex. for(counter = 0; counter < beatlesMembers.length; counter++){
                        console.log(`${beatlesMembers[counter]} is a member of the Beatles`}
                    }

                To add elements to the array:
                .push() method adds the element at the end of the array.

                More array methods: https://www.w3schools.com/jsref/jsref_obj_array.asp

            Objects - collection of key-value pairs
                ex. const pet = {
                    name : "Cheddar",
                    species : "Cat",
                    age : 5,
                    isPlayful : true,
                    hobbies : ["playing", "cuddling", "eating treats"] 
                }

                To get the value of a specific key/property, use the [] or the dot notation
                    console.log(pet.name);
                    console.log(pet["age"]);

                Difference between dot and bracket notations: https://codeburst.io/javascript-quickie-dot-notation-vs-bracket-notation-333641c0f781


                The for-in loop can be used to get both the properties and values of the object
                ex. const object = { a: 1, b: 2, c: 3 };
                    for (const property in object) {
                        console.log(`${property}: ${object[property]}`);
                    }

                A for-of loop can also be used: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of

        v. Functions - small blocks of code that can be repeatedly called and can have various inputs (arguments)

            Syntax:
                function functionName(parameters){
                    code block to execute
                    return statement as needed
                }

            ex:
                function addTwoNumbers(num1, num2){
                    return num1 + num2; //num1 and num2 are the function parameters
                }

                console.log(`The sum of 10 and 18 is ${addTwoNumbers(10, 18)}`); //10 and 18 are the arguments -> are values that my function takes as inputs
                console.log(`The sum of 5 and 99 is ${addTwoNumbers(5, 99)}`);

            ex2: 
                function eat(food){
                    return `I love eating ${food}`;
                }

                console.log(eat(burgers)); //I love eating burgers
                console.log(eat(laksa)); //I love eating laksa

            Q: do all functions need parameters / are parameters optional? no, parameters are optional.

            ex3:
                function helloWorld(){
                    console.log("Hello World");
                } 

                helloWorld();
                helloWorld(); 

            Arrow functions - another way of writing functions and can be assigned to constants
                Syntax:
                (parameters) => {
                    code block to execute
                    return statement
                }
                
                const getDivisibleby3 = (num1) => {
                    let result = (num1 % 3 == 0);
                    return result;
                }

                if(getDivisibleby3(1767)){
                    console.log("Number is divisible by 3");
                else {
                    console.log("Number is not divisible by 3");
                }