# nFrastructure Coding Standard

Repository with all coding standard ruleset for nFrastructure repositories.

## PHP
 
### Installation

1. Add the following to composer.json

   ```json
   "repositories": [
     {
       "type": "vcs",
       "url": "git@github.com:nfrastructuredev/nfrastructure-coding-standards.git"
     }
   ],
   ```
   
   ```json
   "require-dev": {
     "nfrastructuredev/nfrastructure-coding-standards": "^1"
   }
   
   ```

1. Install via composer 

    ```bash
    $ composer install --dev
    ```

1. Add composer scripts into your `composer.json`:

   ```json
   "scripts": {
     "cs-check": "phpcs",
     "cs-fix": "phpcbf"
   }
   ```

1. Create file `phpcs.xml` on base path of your repository with content:

   ```xml
   <?xml version="1.0"?>
   <ruleset name="nFrastructure Coding Standard">
       <rule ref="./vendor/nfrastructure/nfrastructure-coding-standard/ruleset.xml"/>

       <!-- Paths to check -->
       <file>src</file>
       <file>test</file>
   </ruleset>
   ```

You can add or exclude some locations in that file.
For a reference please see: https://github.com/squizlabs/PHP_CodeSniffer/wiki/Annotated-ruleset.xml


### Usage

* To run checks only:

  ```bash
  $ composer cs-check
  ```

* To automatically fix many CS issues:
 
  ```bash
  $ composer cs-fix
  ```