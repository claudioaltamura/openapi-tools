# Part Two - Validator

https://github.com/OpenAPITools/openapi-style-validator

## Petstore example

adapted from 

https://github.com/OAI/OpenAPI-Specification/blob/main/examples/v3.0/petstore.yaml
https://github.com/OAI/OpenAPI-Specification/blob/main/examples/v3.0/petstore-expanded.yaml


## Installation

https://openapitools.github.io/openapi-style-validator/

as CLI, download manually

```https://repo1.maven.org/maven2/org/openapitools/openapistylevalidator/openapi-style-validator-cli/<version>/openapi-style-validator-cli-<version>-all.jar```

https://repo1.maven.org/maven2/org/openapitools/openapistylevalidator/openapi-style-validator-cli/

## Launch

    java -jar openapi-style-validator-cli-1.8-all.jar -s ../petstore-expanded.yaml -o specs/options.json


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

Maven

    [INFO] --- openapi-style-validator:1.8:validate (default-cli) @ openapitools-validator-mvn-example ---
[INFO] Validating spec: petstore-expanded.json
[ERROR] OpenAPI Specification does not meet the requirements. Issues:

[ERROR]         *ERROR* in Operation GET /pets 'summary' -> This field should be present and not empty
[ERROR]         *ERROR* in Operation GET /pets 'tags' -> The collection should be present and there should be at least one item in it
[ERROR]         *ERROR* in Operation POST /pets 'summary' -> This field should be present and not empty
[ERROR]         *ERROR* in Operation POST /pets 'tags' -> The collection should be present and there should be at least one item in it
[ERROR]         *ERROR* in Operation GET /pets/{id} 'summary' -> This field should be present and not empty
[ERROR]         *ERROR* in Operation GET /pets/{id} 'tags' -> The collection should be present and there should be at least one item in it
[ERROR]         *ERROR* in Operation DELETE /pets/{id} 'summary' -> This field should be present and not empty
[ERROR]         *ERROR* in Operation DELETE /pets/{id} 'tags' -> The collection should be present and there should be at least one item in it
[ERROR]         *ERROR* in Model 'NewPet', property 'name', field 'example' -> This field should be present and not empty
[ERROR]         *ERROR* in Model 'NewPet', property 'name', field 'description' -> This field should be present and not empty
[ERROR]         *ERROR* in Model 'NewPet', property 'tag', field 'example' -> This field should be present and not empty
[ERROR]         *ERROR* in Model 'NewPet', property 'tag', field 'description' -> This field should be present and not empty
[ERROR]         *ERROR* in Model 'Error', property 'code', field 'example' -> This field should be present and not empty
[ERROR]         *ERROR* in Model 'Error', property 'code', field 'description' -> This field should be present and not empty
[ERROR]         *ERROR* in Model 'Error', property 'message', field 'example' -> This field should be present and not empty
[ERROR]         *ERROR* in Model 'Error', property 'message', field 'description' -> This field should be present and not empty
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE

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

## Spring Boot example

configuration

			<plugin>
				<groupId>org.openapitools.openapistylevalidator</groupId>
				<artifactId>openapi-style-validator-maven-plugin</artifactId>
				<version>1.8</version>
				<configuration>
					<inputFile>../../petstore-expanded.yaml</inputFile>
				</configuration>
				<dependencies>
					<dependency>
						<groupId>org.openapitools.empoa</groupId>
						<artifactId>empoa-swagger-core</artifactId>
						<version>2.0.0</version>
						<exclusions>
							<exclusion>
								<groupId>io.swagger.core.v3</groupId>
								<artifactId>swagger-models</artifactId>
							</exclusion>
						</exclusions>
					</dependency>
				</dependencies>
			</plugin>


command

    mvn openapi-style-validator:validate


## tag use case

Grouping Operations With Tag

Tagged operations may be handled differently by tools and libraries. 

https://swagger.io/docs/specification/grouping-operations-with-tags/

## Comparison to openapi-generator-cli validate

    openapi-generator-cli validate -i ../petstore-expanded.yaml

    Validating spec (../petstore-expanded.yaml)
    [main] INFO  o.o.codegen.utils.ModelUtils - [deprecated] inheritance without use of 'discriminator.propertyName' has been deprecated in the 5.x release. Composed schema name: null. Title: null
    No validation issues detected.
