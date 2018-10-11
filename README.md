# Back-end Developer Test

This is a simple (and hopefully fun) exercise, used to evaluate your ability to design and build a solution to satisfy a set of requirements. Your solution must come in the form of a **command-line** application (see below for details), and shouldn't take longer than an hour to complete. If you feel that there are any obvious areas for improvement that you could make if you had more time to spend on it, please note them in your README.

You can pick any of **PHP**, **NodeJS** or **Scala** to build your app. You are only **required** to submit a solution in **one** of those languages, but for bonus points you are welcome to complete the test in two, or even all three languages.

Please **do not** fork this repository, because that will make your solution visible to all future candidates!


### Technical Requirements

Your solution must work with the following platforms (depending on your language of choice):

  * PHP `7.0`
  * NodeJS `8.9`
  * Scala `2.12` and Oracle JDK `8`

It will be tested on Ubuntu `14.04`, but that should make no difference to your solution (any Linux distro will do).

You are expected to integrate with the REST API directly, instead of using pre-written integrations (like an SDK), but otherwise you're welcome to use any libraries you like.


### Functional Requirements

The command line application **must**:

  1. Take a single argument specifying the search term, and error out if one is not provided
  2. Using the [Github API](https://developer.github.com/v3/) as a starting point, find all the repositories that have a **description** containing the given search term **as a full phrase** (not just the words individually). To avoid hitting the API rate limit, you should only load **up to 1000** results.
  3. Filter out any repos with an empty "language" (`null` or empty String)
  4. Group the remaining list of repos by "language", and count the number of occurrences for each
  5. Sort the languages by occurrence descending
  6. Output a line for each result, in the `{language}: {count}` format
  7. After the results, on a separate line, output the total number of search results in the format: `=> {total_count} total result(s) found`

For example, using `shampoo` as an input, it should return something like:
```
JavaScript: 6
C#: 2
Emacs Lisp: 1
Jupyter Notebook: 1
HTML: 1
Python: 1
CMake: 1
Go: 1
TypeScript: 1
PHP: 1
=> 29 total result(s) found
```

Please provide a README with basic instructions on how to run your application, and assumptions you made when writing it.

### Evaluation

While your submission must work for any arbitrary search term, it will be tested with the following:

  * `lipstick`
  * `skin care`
  * `mascara`
