# Part One - Validator

https://github.com/OpenAPITools/openapi-style-validator

## Petstore example

copied from https://github.com/OAI/OpenAPI-Specification/blob/main/examples/v3.0/petstore-expanded.yaml


## Installation

https://openapitools.github.io/openapi-style-validator/

as CLI, download manually

```https://repo1.maven.org/maven2/org/openapitools/openapistylevalidator/openapi-style-validator-cli/<version>/openapi-style-validator-cli-<version>-all.jar```

https://repo1.maven.org/maven2/org/openapitools/openapistylevalidator/openapi-style-validator-cli/

## Launch

    java -jar openapi-style-validator-cli-1.8-all.jar -s specs/petstore-expanded.yaml -o specs/options.json


options.json copied from https://github.com/OpenAPITools/openapi-style-validator/blob/master/specs/options.json

example outout

    *ERROR* in Operation GET /pets 'tags' -> The collection should be present and there should be at least one item in it
    *ERROR* in Operation POST /pets 'tags' -> The collection should be present and there should be at least one item in it
    *ERROR* in Operation GET /pets/{id} 'tags' -> The collection should be present and there should be at least one item in it
    *ERROR* in Operation DELETE /pets/{id} 'tags' -> The collection should be present and there should be at least one item in it
    *ERROR* in Model 'NewPet', property 'name', field 'example' -> This field should be present and not empty
    *ERROR* in Model 'NewPet', property 'name', field 'description' -> This field should be present and not empty
    *ERROR* in Model 'NewPet', property 'tag', field 'example' -> This field should be present and not empty
    *ERROR* in Model 'NewPet', property 'tag', field 'description' -> This field should be present and not empty
    *ERROR* in Model 'Error', property 'code', field 'example' -> This field should be present and not empty
    *ERROR* in Model 'Error', property 'code', field 'description' -> This field should be present and not empty
    *ERROR* in Model 'Error', property 'message', field 'example' -> This field should be present and not empty
    *ERROR* in Model 'Error', property 'message', field 'description' -> This field should be present and not empty

