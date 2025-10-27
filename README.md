# PokéAPI Postman Testing Workshop
A brief workshop to teach Postman testing approaches using `pm.test()` and `pm.expect()`, the built-in [Lodash](https://lodash.com/) JS library and [JSON Schema validation](https://learning.postman.com/docs/tests-and-scripts/write-scripts/test-examples/#validate-response-structure) via [ajv](https://www.npmjs.com/package/ajv) (also built in to Postman). Includes a 'solved' version for quick reference and tutor demonstration.

The API used for this workshop is [PokéAPI](https://pokeapi.co/), via its `https://pokeapi.co/api/v2/` REST endpoint.

## Requirements for initial setup/self-study

* A recent version of Postman, on any supported platform (including the web)
* No network restrictions that would prevent you from accessing `https://pokeapi.co/api/v2/{endpoint}` via GET requests. 
* That's it!
 
### Additional requirements for running this as a workshop:
* Some introductory slides to explain the workshop (learning objectives, participant setup, screenshots etc.) - PRs accepted if anyone would like to make a generic version of this.
* Some willing/voluntold workshop participants.

## Instructions (per-participant)

1. Import `PokeAPI API Testing Workshop.postman_collection.json` into Postman as a new collection.
2. Create a new Postman environment, with the `baseUrl` variable set to `https://pokeapi.co/api/v2/`, and ensure that this is set as your current environment.
   * Other variables (if not already set) will be set automatically when executing the relevant endpoints, via 'Post-request scripts'.
   * For example `testPokemonId` will be automatically set to `25` and `testPokemonName` will be set to `pikachu`, but the tests should still pass if you update these variables to (e.g.) `132` and `ditto` respectively - the name of the Pokémon must match the ID, though.
3. Execute an endpoint to see the test results, then visit the tests tab to find and fix any failing tests.
   * Some tests will have been deliberately failed using `pm.expect.fail()` - make sure to delete these lines before writing any test code.
5. To view the solved version with passing tests, import `PokeAPI API Testing Workshop_SOLVED.postman_collection.json` - ensure that the same Postman environment is set.

## Tips

* JSON responses with lots of nested objects are quite tedious to write schemas for. This might be a good opportunity to discuss how your JSON schemas could be auto-generated.
* While writing a schema by hand, you should regularly check that your conditions are actually being checked properly. For example, try changing the type of a property from `object` to `string` (or `string` to `array` etc.), execute the endpoint and confirm that the schema validation test fails as you expect.
  * If the test passes when you expect it to fail, check that the syntax of your schema is correct. Postman will flag missed commas and braces, but it won't tell you if the JSON schema validation syntax (`properties`, `items`, `required` etc.) has been used correctly.
* In the final exercise the `additionalProperties` property on the outer object is set to `false` by default. You may wish to set this to `true` until you have finished adding all the properties, so you can test that the rest of the schema is working as expected.
* Use the [JSON Schema Reference](https://json-schema.org/understanding-json-schema/reference/type) to find possible approaches for validating each data type within a JSON response.
