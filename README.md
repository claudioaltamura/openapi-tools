# openapi-tools
Accompanying sources to the blog article series OpenAPI Tools

### Install generator CLI

    npm install @openapitools/openapi-generator-cli -g

https://openapi-generator.tech/docs/installation

### Generate

    npx @openapitools/openapi-generator-cli generate -i  part-one-validator/specs/petstore-expanded.yaml -g asciidoc -o asciidoc
