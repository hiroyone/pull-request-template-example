# Best Practices for Reviewing Pull Requests in projects

**Are you really confident in reviewing your colleague's code when they submit a pull request to you?**

**Can you proudly answer the crucial qualities you should look into in the code?**

To be honest, I had been not confident at all for a long time. I was so afraid and overwhelmed to see pull requests with massive, unstructured lines of code changes submitted by a diverse level of other software engineers, even though I had already gained confidence in my programming skills.

However, I started to review my colleague's pull request in a million-dollar enterprise project which was so large and challenging. I have done more than 100 code reviews intensively in a couple of months and discovered solid insights into essential perspectives every reviewer should have in a practical and sustainable way.

I am happy to share them below.

---

## No.1: Traceable and Revertible Pull Requests

Pull requests should be traceable and revertible after your review so that we can analyze, debug, or even revert code commits long days after we find a bug in a program.

**Don't:** Your review discovers all kinds of bugs

Catching all kinds of bugs with human eyes is too much time-consuming and almost impossible. Business logic functionalities should be guaranteed by (automatic) testings rather than manual code reviews.

**Do:** Prepare a crystal-clear pull request template

```
## Description

Please write a summary of the changes in this pull request.

Fixes # (issue)

## Changes

Please write a list of this PR's changes here.

## Todos

Please write a list of future changes here.

## How can we see the results or reproduce them?

Please attach screenshots or videos so that reviewers can easily confirm what features are implemented.

## How Has This Been Tested?

Please describe the tests that you ran to verify your changes.

- [ ] Unit test
- [ ] Integration test
- [ ] End-to-end test
- [ ] System test

## How do you want others to review your code?

- [ ] Commit by commit
- [ ] Entire diff
- [ ] Others

```

This is from [my repository](https://github.com/hiroyone/pull-request-template-example).

**What about the pull request size? Shouldn't it be small?**

Yes, but there is no way to enforce this systemically. It is already too late when an inexperienced programmer posts a large pull request.

## No.2: Remove Poor Code but Accept Mediocre Code

**Don't:** Pursue and enforce the best implementations on every bit of code. Conquer both poor and mediocre code.

**Do:** Comment only on poorly implemented code that significantly impairs the robustness of the repository's structure.

The best code is mostly subjective, contextual, hard to prove.
The poor code is self-evident and easy to spot.

**Examples of Poor Code**

- Duplicated code
- More than two nested something (functions, objects)
- Misleading variable names
- More than ten function arguments
- Hard-coding: mixes of logic and data

**Examples of Mediocre code**

- Lengthy function name
- Less popular or outdated syntax
- Non-conventional variable name but it still makes sense (e.g. `addMore` instead of `readMore` )

It is good to avoid an unnecessary dispute with your colleagues on tiny code performance or styles. A few disagreements over minor things with colleagues would ruin the relationship and the atmosphere in a long-run project.

However, experienced programmers tend to pursue the best implementations and occasionally enforce that to others because they improved their programming skills that way

We can never reach the best practices in our repository before the tech stacks get outdated. But every year, a gazillion of new languages, frameworks, tools are invented and integrated with the working code repository to bring about more innovations - productivity and creativity.

On the other hand, there are also a lot of software development principles that are universally true, and no project would be successful if these principles were ignored.

Therefore, the balanced approach is to cut out the only destructive code, which makes it hard to refactor or fix the repository in the future.
