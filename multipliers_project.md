# Multipliers Project

We will use the `TDD` approach for Multipliers Project development, performing this approach includes the following steps:

1.  Adding test
2.  Run all tests and see if any new test fails
3.  Writing some code
4.  Run tests and Refactor code
5.  Repeat

```

                         +
                         |
                   +-----+------+
             +---->| add a test |<--------+
             |     +-----+------+         |
             |           |                |
        pass |           |                |
             |           v                |
             |  +-------------------+     |
             +--+ execute the tests |     |
                +--------+----------+     |
                         |                | pass
                         | fail           |
                         v                |
            +--------------------------+  |
         +->| make changes to the code |  |
         |  +------------+-------------+  |
         |               |                |
    fail |               |                |
         |               v                |
         |      +-------------------+     |
         +-----+| execute the tests +-----+
                +--------+----------+
                         |
                         v
               pass, development stops

```

---

### Project Structure

#### assets

This directory contains assets and resources, an asset is a file that is bundled and deployed with the app, and is accessible at runtime. Common types of assets include `static data, configuration files, icons, images, fonts, etc`.

#### exceptions

Exceptions Directory contains exception classes. An Exception class should extend the `MultipliersException` class as the base class.

#### core

The core directory contains any common classes and any class that may be used by more than one feature.

#### helpers

A helper class is used to assist in providing some functionality, which isn't the main goal of the application or class in which it is used, we can put all helper classes here and categorize them by type and usage

#### blocs

This directory contains blocs that will use by feature, each bloc should have `bloc`, `event`, and `state` classes that organize under corresponding bloc directory.

#### pages

This directory holds app page classes, a page is a widget that provides a screen with which users can interact to do something.

#### services

Contains dependency injector, mock generator, theme provider, and other services

#### widgets

This directory has custom widgets which are used in multiple different pages

#### theme_provider

Contains application theme-related classes

#### Notes:

- We should logically breakdown our app components under several features
- These directories may have several sub-folders for categorizing structure base on logical connections between components.
- Test files should reside inside a `test` folder at the root of the application.
- Unit and Widget tests must be in a `test` folder. The integration test must go in a separate directory called `test_driver` and both folders must be at the same level as the lib folder.
- Test files should always end with `_test.dart`, this is the convention used by the test runner when searching for tests. Also, test directories should mirror exactly the project structure for ease of finding the corresponding tests for each app component that needs testing.
- If test classes need to have mock data, add a file with `_data` postfix and put it aside test file.

```
.
├── assets
│   ├── fonts
│   ├── icons
│   └── ...
├── lib
│   ├── core
│   │   ├── exceptions
│   │   ├── helpers
│   │   ├── services
│   │   │   ├── dependency_injector
│   │   │   └── ...
│   │   ├── theme_provider
│   │   └── ...
│   └── features
│       ├── feature 01
│       │   ├── blocs
│       │   ├── exceptions
│       │   ├── pages
│       │   └── widgets
│       └── feature ...
├── test
│   ├── core
│   └── features
│       ├── feature 01
│       │   ├── blocs
│       │   ├── exceptions
│       │   ├── pages
│       │   └── widgets
│       └── feature ...
└── test_driver
    └── ...

```
