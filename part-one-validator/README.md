# Part One - Validator

https://github.com/OpenAPITools/openapi-style-validator

## Petstore example

adapted from 

wget https://github.com/OAI/OpenAPI-Specification/blob/main/examples/v3.0/petstore.yaml
https://github.com/OAI/OpenAPI-Specification/blob/main/examples/v3.0/petstore-expanded.yaml


## Installation

https://openapitools.github.io/openapi-style-validator/

as CLI, download manually

```https://repo1.maven.org/maven2/org/openapitools/openapistylevalidator/openapi-style-validator-cli/<version>/openapi-style-validator-cli-<version>-all.jar```

https://repo1.maven.org/maven2/org/openapitools/openapistylevalidator/openapi-style-validator-cli/

## Launch

    java -jar openapi-style-validator-cli-1.8-all.jar -s specs/petstore-expanded.yaml -o specs/options.json


options.json copied from https://github.com/OpenAPITools/openapi-style-validator/blob/master/specs/options.json

### Example output

    *ERROR* in Operation GET /pets 'summary' -> This field should be present and not empty
    *ERROR* in Operation POST /pets 'summary' -> This field should be present and not empty
    *ERROR* in Operation GET /pets/{id} 'summary' -> This field should be present and not empty
    *ERROR* in Operation DELETE /pets/{id} 'summary' -> This field should be present and not empty
    *ERROR* in Model 'NewPet', property 'name', field 'example' -> This field should be present and not empty
    *ERROR* in Model 'NewPet', property 'name', field 'description' -> This field should be present and not empty
    *ERROR* in Model 'NewPet', property 'tag', field 'example' -> This field should be present and not empty
    *ERROR* in Model 'NewPet', property 'tag', field 'description' -> This field should be present and not empty
    *ERROR* in Model 'Error', property 'code', field 'example' -> This field should be present and not empty
    *ERROR* in Model 'Error', property 'code', field 'description' -> This field should be present and not empty
    *ERROR* in Model 'Error', property 'message', field 'example' -> This field should be present and not empty
    *ERROR* in Model 'Error', property 'message', field 'description' -> This field should be present and not empty

## Things to validate

    API Info
    
    API license must be present and non-empty string
    API description must be present and non-empty string
    API contact must be present and non-empty string

    Operations
    
    OperationId must be present and non-empty string
    Operation description must be present and non-empty string
    Operation must have a tag and non-empty string
    Operation summary must be present and non-empty string

    Models
    All model properties must have examples
    All model properties must have descriptions
    All required properties must be listed among the properties

    Naming convention
    Enforce naming convention for paths, parameters (path, query and cookie), headers and properties
    underscore_case
    UNDERSCORE_UPPER_CASE
    camelCase
    hyphen-case
    Hyphen-Upper-Case

https://github.com/OpenAPITools/openapi-style-validator


## tag use case

Grouping Operations With Tag

Tagged operations may be handled differently by tools and libraries. 

https://swagger.io/docs/specification/grouping-operations-with-tags/