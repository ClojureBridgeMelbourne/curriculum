Making Your First Program
=========================

Now that you know a bit about how to write Clojure code, let's look at how to create a standalone application.

In order to do that, you'll first create a *project*. You'll learn how to organize your project with *namespaces*. You'll also learn how to specify your project's *dependencies*. Finally, you'll learn how to *build* your project to create the standalone application.

## Create a Project

Up until now you've been experimenting in a REPL. Unfortunately, all the work you do in a REPL is lost when you close the REPL. You can think of a project as a permanent home for your code. You'll be using a tool called "Leiningen" to help you create and manage your project. To create a new project, run this command:

```clojure
lein new clojurebridge-sample
```

This should create a directory structure that looks like this:

```
| .gitignore
| doc
| | intro.md
| LICENSE
| project.clj
| resources
| README.md
| src
| | clojurebridge_sample
| | | core.clj
| test
| | clojurebridge_sample
| | | core_test.clj
```

There's nothing inherently special or Clojure-y about this project skeleton. It's just a convention used by Leiningen. You'll be using Leiningen to build and run Clojure apps, and Leiningen expects your app to be laid out this way. Here's the function of each part of the skeleton:

- `project.clj` is a configuration file for Leiningen. It helps
  Leiningen answer questions like, "What dependencies does this
  project have?" and "When this Clojure program runs, what function
  should get executed first?"
- `src/clojurebridge_sample/core.clj` is where we'll be doing our
  Clojure coding for a while.
- The `test` directory contains tests, which we won't be covering.
- `resources` is a place for you to store assets like images; we won't
  be using it today.


## Organization

As your programs get more complex, you'll need to organize them. You organize your Clojure code by placing related functions and data in separate files. Clojure expects each file to correspond to a *namespace*, so you must *declare* a namespace at the top of each file.

Until now, you haven't really had to care about namespaces. Namespaces allow you to define new functions and data structures without worrying about whether the name you'd like is already taken. For example, you could create a function named `println` within the custom namespace `my-special-namespace`, and it would not interfere with Clojure's built-in `println` function. You can use the *fully-qualified name* `my-special-namespace/println` to distinguish your function from the built-in `println`.

A namespace exists in the file `src/global_growth/core.clj`. Open it, and find this line:

```clojure
(ns global-growth.core)
```

This line establishes that everything you define in this file will be stored within the `global-growth.core` namespace.

## Open in lighttable

***NOTE: Tested on OSX only: please see Jen if it doesn't work for you!***

In lighttable, go to File->Open folder.

Select the new folder that was created for your project (clojurebridge-sample) and click 'upload'.

In lighttable, locate core.clj and click it to open it.

Hit ctrl-space (or apple-space) and select Instarepl: Make current
editor an Instarepl

Wait for a little while and you should have an instarepl-enabled
editor. You can save changes to this file and even check into source
control if that's your thing.

