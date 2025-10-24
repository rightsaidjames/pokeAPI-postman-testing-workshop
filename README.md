# PokéAPI Postman Testing Workshop
A brief workshop to teach Postman testing approaches using `pm.test()`, the built-in [underscore](https://www.npmjs.com/package/underscore) JS library and [JSON Schema validation](https://learning.postman.com/docs/tests-and-scripts/write-scripts/test-examples/#validate-response-structure) via [ajv](https://www.npmjs.com/package/ajv) (also built-in to Postman). Includes a 'solved' version for quick reference and tutor demonstration.

The API used for this workshop is [PokéAPI](https://pokeapi.co/), via its `https://pokeapi.co/api/v2/` REST endpoint.

## Requirements for initial setup/self-study

* A recent version of Postman, on any supported platform (including web)
* A clean Postman environment, with the `baseUrl` variable set to `https://pokeapi.co/api/v2/`
* * Other variables (if not already set) will be set automatically when executing the relevant endpoints.
  * For example `testPokemonId` will be automatically set to `25` and `testPokemonName` will be set to `pikachu`, but the tests should still pass if you update these variables to (e.g.) `132` and `ditto` respectively.
* That's it!
 
### Additional requirements for running this as a workshop:
* Some introductory slides to explain the workshop (learning objectives, participant setup, screenshots etc.) - PRs accepted if anyone would like to make a generic version of this.
* Some willing/voluntold workshop participants.

## Setup

[TODO]
