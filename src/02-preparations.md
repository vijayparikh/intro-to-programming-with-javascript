# Preparations

Getting started with JavaScript is easy. You can jump into your browser console and start writing JavaScript right now! However, a bit of preparation goes a long way, and learning some background should make your JavaScript journey a rewarding and productive experience. In this chapter, we'll show you how to run JavaScript, determine what the community coding conventions are, and where to go for help and documentation.

## Runtime Environments

Depending on the problem domain and environment, applications must access various resources provided by the machine, such as networking infrastructure, RAM, sensors, and the GPU to do useful work. A runtime environment is an execution environment that lets an application program access system resources and provides the tools the application needs to operate.

In some cases, these tools let the application interact with the outside world. In others, they let the operating system interpret and understand what the application is doing. In other words, the runtime environment turns an application from a set of instructions into something that performs actual work.

The following is background information. You do not need to memorize it.

The phrase **_programming language_** is a fuzzy term that refers to a variety of different ways to tell a computer what to do. In a strict sense, a programming language is a set of syntactic and semantic rules that describe a formal language and must be able to express the steps that a machine needs to perform to convert some input to an output.

Before the computer can perform those steps, though, the program needs to be converted to a form the computer can understand. Programs called compilers and interpreters perform this conversion. At their most basic level, **_compilers_** and **_interpreters_** are similar: they both translate a program written in a specific programming language to something that the computer can execute, typically referred to as "1s and 0s" since all information on digital computers gets stored as 1s and 0s.

Compilers and interpreters differ primarily in what they do with those 1s and 0s. Compilers produce an output file that the computer can run directly, perhaps after some additional processing called linking. Interpreters, however, don't produce 1s and 0s that the computer can run directly - instead, the interpreter runs the interpreted code directly, or perhaps passes it on to a companion program.

JavaScript, at its heart, is an interpreted language. However, for performance reasons, most modern JavaScript engines employ a special kind of compiler called a **_Just In Time (JIT) compiler_** that takes the interpreted code one step further and lets the computer run the result.

For our purposes, this distinction between compilers and interpreters is unimportant. However, you'll encounter both terms in your career, and should generally have some sort of idea of whether you're working with a compiled or interpreted language, even if you don't fully understand the mechanics and ramifications.

When an application accesses an operating system's resources, something must ensure that the operating system provides them in a regulated and safe manner. An **_Application Programming Interface (API)_** provides that functionality: it describes the scheme and format that a programmer can use to securely access resources, with the operating system acting as an intermediary. A runtime environment typically adds another layer of abstraction on top of the operating system's API to make these resources available with a higher-level (i.e., more accessible) API. The compiler/interpreter and the operating system's APIs together make up a runtime environment. In other words, they provide the tools that an application needs to run. The APIs needed for one runtime environment can differ from those needed in another environment.

Besides access to a computer's resources, an application programmer also needs tools for debugging and profiling her code to find and fix bugs in her program. When you add these developer tools to the mix, you get a development environment. For our purposes, we'll treat the developer tools as part of the runtime environment.

In the JavaScript world, there are two major runtime environments you are likely to encounter: the browser and Node.js. You may also encounter a number of less common environments. Let's take a look at the major JavaScript runtime environments.

### Browser

The web browser was the original JavaScript runtime environment, and it's still the most dominant. JavaScript running in the browser is far more ubiquitous than JavaScript running anywhere else. Almost every browser has a JavaScript engine built into it.

JavaScript in the browser has two main purposes: 1) to programmatically alter web pages based on user actions; and, 2) to exchange messages with a server over a network. To perform the first task, the programmer needs an API through which they can manipulate the structure and appearance of the HTML page. For the second task, they need an API that lets them use the operating system's ability to send and receive messages over a network. Almost every browser provides a way to accomplish these tasks, though there are some compatibility issues between browsers. The DOM (Document Object Model) API lets you manipulate the structure and appearance of a web page, while the XHR (XMLHttpRequest) interface and the Fetch API let you communicate with a server.

Runtime environments must provide tools that let developers debug and inspect programs. Browsers are no different. All major browsers provide a "Developer Tools" feature that includes a REPL, a debugger, a network inspector, a performance profiler, and more.

### Node.js

As mentioned in the previous chapter, Node.js is a runtime environment that turns JavaScript into a general-purpose programming language that can run applications on almost any system. The creators of Node.js took the open-source Chrome V8 JavaScript engine and added APIs and tools required for desktop and server computing.

A general-purpose programming environment, like Node.js, needs the following minimal capabilities:

- The ability to read and write disk files (disk I/O);
- The ability to read and write via the terminal (standard I/O);
- The ability to send and receive messages over a network (network I/O);
- The ability to interact with a database.

Node.js has APIs and packages for all these tasks and more. It also provides an interactive REPL (read-eval-print loop) where you can execute JavaScript commands and get instant results. Like any useful runtime environment, Node.js provides tools for debugging and inspecting programs at runtime. Unfortunately, the debugging and inspecting tools are somewhat difficult to use directly; instead, you generally have to use a browser, and Google Chrome in particular. We will not discuss Node debugging in this book.

### Other JavaScript Runtime Environments

Apart from browsers and Node.js, you can find JavaScript in some other environments. For example, Adobe's Acrobat supports JavaScript to automate and animate elements in a document. Other environments include ActionScript and GNOME shell. In this book, we'll limit our focus to the browser and Node.js runtime environments.

## Installation

If you have a contemporary browser installed on your computer, you already have everything you need to run all the code in this book. However, you'll find that Node.js is more convenient than using your browser. With Node.js, you don't need to embed your JavaScript file in a webpage to run it; in a browser, you must load your JavaScript from an HTML file. We recommend Node.js version 12.0.0 or higher to work with the examples and exercises in this book. You can find official installation instructions for your platform on Node's website:

- [Installation instructions for macOS](https://nodejs.org/en/download/package-manager/#macos)
- [Installation instructions for Debian/Ubuntu Linux](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions)
- [Installation instructions for Windows](https://nodejs.org/en/download/package-manager/#windows)

The quickest way to determine whether Node.js is installed is to try running it. Open your Terminal application, or the Windows Command Prompt if you're on Windows, and run the command:

``` bash
$ node -v       # -v requests the version number
v12.4.1
```

Make sure this command displays version v12.0.0 or higher. In fact, we recommend installing the latest version of Node that you can.

The Node installation process should also install **npm** — Node's package dependency manager—for you, but it doesn't hurt to check:

``` bash
$ npm -v        # -v requests the version number
6.5.0
```

If you can't or don't want to install Node.js on your computer, you can use web-based programming environments like [repl.it](https://replit.com/) to run the programs in this book. However, we recommend installing Node.js: it's a powerful and useful companion for learning JavaScript.

## Using a Code Editor

You'll be using a code editor to write code. A code editor is used to create plain text documents with no styling or formatting. If you already have a favorite code editor (e.g., Vim, TextMate, Emacs, Notepad++, etc.) you can use it to work through this book. However, if you do not have a preferred code editor, we recommend using [Visual Studio Code](https://code.visualstudio.com/) (also known as VSCode). It's free and "built on" open-source. It's a highly polished product that is both pleasant to look at and pleasant to use. Most surprisingly, perhaps, is that it comes from Microsoft. Its popularity is growing rapidly in the developer community. At the time of this writing, the plugin ecosystem isn't quite as vast and varied as those for Sublime Text and Atom (see below), but it's growing at a robust pace. If you don't have a preference, this is the option we recommend.

Two other great editors that work very similarly to VSCode are [Atom](https://atom.io/) and [Sublime Text](http://www.sublimetext.com/). Atom is open source and completely free to use and modify, while Sublime Text is neither free nor open source (it will ask you, but not require you, to purchase a license). Both editors are powerful and fast and are in widespread use. They both are easy to learn and work well "out of the box". They also have a wealth of add-on packages available.

All 3 of these editors come in Mac, Windows, and Linux versions.

Avoid using word processors or advanced text editors when writing code: their focus is writing, not coding, and they often inject invisible characters or whitespace into the document to help format and style it. While that can make your prose look great, it doesn't work well with code. Code written with a word processor may not run at all, even if you copy and paste the code into a code editor before saving it.


## Stylish JavaScript

The JavaScript community has some stylistic guidelines that help make JavaScript code easier to read and write. Not all of the guidelines agree on all points, but there's plenty of overlap. Adhering to the style conventions of a programming language is helpful and meaningful even if you don't agree with every convention. You probably won't be the sole person developing and maintaining a software project; adhering to a particular style convention helps your teammates and future maintainers understand your code. It's hard enough to understand code written by someone else; don't make it harder with unusual or non-standard stylistic choices.

The conventions we'll talk about in this section are specific to the JavaScript community. Other programming languages—and even some JavaScript sub-communities—may have different preferences about each guideline.

Here's a short list of guidelines that we recommend. If you already work with a formal set of guidelines, please feel free to use them. If you don't, our suggestions should help you write readable code.

- Set your text editor to use space characters—not tabs—for indentation. The editor should also insert spaces if you press the "tab" key on your keyboard.

- Set your text editor to use 2 spaces for indentation and when converting tab characters to spaces.

- Try to limit lines to 80 characters. This limit isn't a universal preference, but it helps readability. Not all developers have massive screens or good eyesight.

- JavaScript uses the character sequence // to mark the beginning of a comment. Such comments run through the end of the line.

``` JavaScript
let answerToUltimateQuestion = 42; // initializing a variable
let aRoundNumber = 3.141528;       // another comment
```

You can also use /* and */ for multiline comments and when you want to embed comments in the middle of a line:

``` JavaScript
/* This is a multi-line comment.
   It can span any number of lines.
   The command ends when you see
   an * followed by a / as shown
   here ==> */

// You can also use /* and */ to embed comments in the middle of a line:
let area = w /* width */ * h /* height */;
// You should avoid embedded comments
```

Programmers use comments to leave notes for other programmers or themselves at a later point in time; however, don't overdo your comments. Let your code do the talking instead.

- When writing a code block or function body with curly braces, write the opening brace on the same line as the function name or conditional expression. Use a single space just before the opening brace:

``` JavaScript
if (isOk()){              // bad
  // do something
}

if (isOk())               // bad
{
  // do something
}

if (isOk()) {             // good
  // do something
}


function isOk(){          // bad
  // do something
}

function isOk()           // bad
{
  // do something
}

function isOk() {         // good
  // do something
}
```

- Use spaces between operators and operands to make your code less cluttered and easier to read:

``` JavaScript
let sum=x+5;              // bad
let sum = x + 5;          // good
```

- Use semicolons to terminate each logical line of code unless the line ends with {, }, or :. See the next section for details.

That covers the essential style conventions that you need to get started. If you want more information about JavaScript styling, we recommend [Airbnb's JavaScript style guide](https://github.com/airbnb/javascript). Check it out, but don't try to memorize all of the rules right away.

## Naming conventions

Naming conventions are similar to style conventions (and are often discussed together), but JavaScript naming conventions have more gray areas and complexity than most languages, so we'll discuss them separately.

- Use camelCase formatting for most variable and function names. Such names begin with a lowercase letter. If the name contains multiple words, each subsequent word should begin with an uppercase letter:

``` JavaScript
let answerToUltimateQuestion = 42;     // initializing a variable
function fourScoreAndSevenYearsAgo() { // defining a function
  // do something
}
```

- Some function names -- constructor functions -- should normally use PascalCase (also known as CamelCase -- with a capital C) names. For instance:

``` JavaScript
function DomesticCat(name) {           // defining a function
  // do something
}
```

We discuss constructors briefly a little later.

- Use uppercase names with underscores (SCREAMING_SNAKE_CASE) to represent constants that serve as __unchanging configuration values__ in your program.

``` JavaScript
const INTEREST_RATE = 0.0525;
const COURSE_NUMBER = 'JS101';
const HOST = 'launchschool.com';
const FIRST_LETTER = 'a';             // magic number
const LAST_LETTER = 'z';              //
```

We also use SCREAMING_SNAKE_CASE for constants that represent so-called magic numbers (which may not actually be numbers) -- constants that are important to your program in some way but not as configuration values. For instance:

``` javascript
const SECONDS_PER_MINUTE = 60;
const OUNCES_PER_POUND = 16;
const METERS_PER_KILOMETER = 1000;
const PI = 3.141528;
const INPUT_PROMPT = '==>';
const TODAY = new Date();
```

Constants used to store functions (a feature we'll learn about later) should follow the same rules as function names: use camelCase for most functions, and PascalCase for constructor functions.

``` JavaScript
const sayHi = function() {
  console.log("Hi!");
};

const Pet = function(name) {
  this.name = name;
};
```

For all other constants, the rules are much more flexible. You may use camelCase, PascalCase, or even SCREAMING_SNAKE_CASE. Use your personal preferences and any guidelines laid out by your teammates to choose your style.

``` JavaScript
const greetings = `Hi! How are you today?`;
const DeleteAllTodoLists = "DELETE FROM todolists";
const FIND_TODOLIST = `SELECT * FROM todolists WHERE id = ${id}`;
```

All names -- variables and constants as well as functions -- should use the alphabetic and numeric characters only, though SCREAMING_SNAKE_CASE names may use underscores as well. The first character must be alphabetic. Do not use consecutive underscores nor should you use names with underscores at the start or end of the name.

## On Semicolons

When you read JavaScript documentation, books, and articles, most show code that uses semicolons (;) to terminate most statements and expressions, so code ends up looking like this:

``` JavaScript
let x = 3;
let y = 5;

if (x === y) {
  console.log("x is equal to y");
} else {
  console.log("x is not equal to y");
}
```

As you can see, most lines end with a semicolon; there are exceptions like blank lines and lines that end with { or } and a few other situations. Most JavaScript developers use this style. You should, too, at least while you're at Launch School. At first, it's a bit tricky trying to decide whether you need a semicolon, but JavaScript is forgiving. The style becomes so automatic after a short period that you may find yourself typing semicolons everywhere you write something.

A few sources omit the semicolons entirely:

``` JavaScript
let x = 3
let y = 5

if (x === y) {
  console.log("x is equal to y")
} else {
  console.log("x is not equal to y")
}
```

A little-known fact is that JavaScript automatically, but invisibly, inserts semicolons where it needs them. Thus, you can omit semicolons from most code. Some experienced developers take advantage of this mechanism and use (and promote) a no-semicolons-ever style. However, the style requires care: the insertion mechanism makes mistakes when it sees your code differently than you intended. That can be tricky to diagnose when it inserts a semicolon where you don't expect or want one. Thus, we discourage using the no-semicolons style in our courses.

The main reason we mention this at all is that we use two different styles to display JavaScript code in this book: traditional and REPL style. Since the REPL style omits semicolons, it's worth knowing why we can do that.

In traditional style, we show the code as you would enter it in a file before running it. There is no special markup to show prompts, return values, or outputs. In this style, we use semicolons consistently. If we need to show some return values or outputs, we'll use comments:

``` JavaScript
function greeting() {
  console.log('Get ready!');
}

greeting(); // => Get ready!
```

In REPL style, we show code in a way that resembles a Node REPL session or a session in your browser console. A > prompt precedes each statement or expression that we expect you to type. We also precede return values with an = to distinguish them from console outputs that have no prefix at all. Note: don't type the > when entering commands and node doesn't display the =.

``` javascript
> greeting()
Get ready!   // console output
= undefined  // return value of greeting();

> 2 + 2
= 4          // return value of 2 + 2
```

Of particular note with REPL style is that we almost never use semicolons. You can type the semicolons if you want, but you don't have to. For the most part, the work you do in a REPL or console session probably won't lead to semicolon insertion issues.

## The Command Line

This section discusses the commands that you need to run and test JavaScript code from the command line. It's by no means exhaustive, but it's enough to get you started. In particular, we'll take a quick peek at Node's interactive coding environment, the Node REPL, which is where you can test JavaScript code snippets in the terminal.

**Note to Windows Users**: The commands we show below may not work from Windows' default command prompt. We recommend that all Windows developers get familiar with a terminal emulator or with Powershell and issue these commands in that environment.

## Command Line Commands

We assume that you know how to find the command line on your computer and enter commands. When you see the $ symbol in our code examples, it represents the command line prompt. The prompt may look different on your computer, which is fine; it varies depending on the machine you are working on and your local configuration. Note: **don't** type the prompt when entering commands.

We'll also refer to the command line as the terminal ("type in your terminal"), and we may sometimes talk about the terminal as the command line ("print to the command line"). The intent is generally clear from context.

Let's walk through some simple commands. Note that lines that begin with # are comments; you don't have to enter them.

``` bash
# Create a folder named new_dir
mkdir new_dir

# Navigate into the new_dir folder
cd new_dir

# Create a file named new_file.js
touch new_file.js

# Delete the new_file.js file
rm new_file.js

# Navigate out of the current folder to the one above it
cd ..

# Delete the new_dir folder
rmdir new_dir
```

You can remove the directory and file at the same time with rm -R. Let's repeat the above steps, but this time we'll delete new_dir and the file simultaneously.

``` bash
# Create a folder named new_dir
mkdir new_dir

# Navigate into the new_dir folder
cd new_dir

# Create a file called new_file.js
touch new_file.js

# Navigate out of the current folder to the one above it
cd ..

# Delete the new_dir folder and the file new_file.js
rm -R new_dir
```

Use **extreme** caution with the rm command. It's destructive and has no built-in way to recover from deleted files. It takes as much effort to wipe out thousands of files and directories with rm as it takes to delete a single file. If in doubt, use your file navigation program (e.g., Explorer or Finder) and delete files and folders that way; it's slower but safer.

That's all the commands you'll need in this book. If you want to gain more comfort and experience with the command line, many books and online tutorials go into far more depth.
