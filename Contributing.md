# Contribute to ONGR bundles

First of all thank you for contributing to ONGR!

Before you start to work on your PR here are some guidelines that you need to follow. 
We are focusing on robust, code base clean and future proof, so we expect the same from you :wink:.


## Development discussion

Discussion regarding issues, bugs, new features, and questions about implementation of new features takes place in the 
[![Join the chat at https://gitter.im/ongr-io/support](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/ongr-io/support).
 Before start to work on some PR we recommend to come and ask about it, just to make sure you know everything and your work will give a benefit.


## Which branch ??

We only accept pull requests to master branch. You should only open pull requests against the master branch. 
Otherwise we cannot accept the pull request. Don't worry we will take care for other versions branch'es by our self.


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