# Contribute to ONGR bundles

First of all thank you for contributing to ONGR!

Before you start to work on your PR here are some guidelines that you need to follow. 
We are focusing on robust, code base clean and future proof, so we expect the same from you :wink:.

## Which branch ??

This depends on what contribution you want to make. First of all, create an issue about the problem you are facing, fork the repository and then follow the steps below.

### Bugs

If you've found a bug, first double check the documentation or contact ONGR team in the chat if you're not misusing the components.
 If it really looks like a bug, create an issue about it, providing clear title, description and, if possible, examples of the environment that the problem occurs.
 Now you must determine which stable version of the component was the one that the feature holding the bug in question was first introduced.
 In your git fork of the component create a new topic branch from the branch that represents that version. For example if the current stable
 version is `3.0`, but the feature that has the bug you want to fix was introduced in `1.0`, you will have to create the branch and create a a pull request
 to the branch `1.0`. When your changes will be merged, the changes will be applied to all higher branches and we will release a patch that holds your changes.
 Lastly, don't forget to mention the issue number that the bug fix corresponds to at the bottom of your pull requests description, like so: `closes #34`.

### New features

The procedure of submitting a new feature is somewhat similar, you should also engage in a discussion to clarify the details of the feature, open an issue about it
 and then start working on it. The difference from submitting a bug fix here is that the pull requests with the new features should be submitted to the `master` branch
 of the components GIT repository. The `master` branch is dedicated for development of new features that are added in the new versions of the ONGR components.


## Coding standard

For the all code we use [PSR-2](http://www.php-fig.org/psr/psr-2/). Before submitting pull request you should check if your code pass.
We are using [Travis CI](https://travis-ci.org) to perform all checks and the style check is one in the check list.
 
To check code style we recommend to use [code sniffer](https://github.com/squizlabs/PHP_CodeSniffer). You can run it directly from vendors:

```bash

vendor/bin/phpcs -p --standard=PSR2 --ignore=vendor/,Tests/app/ ./

```

> We assume that you already updated bundle's vendors via composer.


Some small issues related with spaces,new lines and etc might be fixed with `phpcbf` which comes together with code sniffer. To perform a fixes run:

```bash

vendor/bin/phpcbf -p --standard=PSR2 --ignore=vendor/,Tests/app/ ./

```


## Tests

At the ONGR we have 2 types of tests. There are Functional and Unit tests. Before submitting a pull request make sure you are not
 introducing lower code coverage than before. We are using [Coverals.io](https://coveralls.io) to perform a check. If there will be lower
 test coverage the pull request will fail.
 
* **Unit tests**: For Unit tests we are testing only current class/function behaviour with "black box" testing. We provide some input and 
 looking to get predefined output. There cannot be any third party connection or relation within a class. If there are some, everything has to be mocked.
 The structure of Unit tests must be mirrored with original bundle file structure.
* **Functional tests**: With functional we test some functionality chain. e.g. In `ElasticsearchBundle` we are testing document insert. Any third party resource can be used.

To run a tests we are using [PHP Unit](https://github.com/sebastianbergmann/phpunit).

To run it simply call: 

```bash

vendor/bin/phpunit

```

> We assume that you already updated bundle's vendors via composer.


## Docs

Documentation is very important. If your pull request introduces some changes or a new feature, make sure you update a docs within the same pull request.
Docs are written in Markdown and are located in each bundle at `Resources/doc`. 
