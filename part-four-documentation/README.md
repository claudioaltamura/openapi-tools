# Part Four - Documentation

## Install generator CLI

    npm install @openapitools/openapi-generator-cli -g

https://openapi-generator.tech/docs/installation

## Generate documentation

    npx @openapitools/openapi-generator-cli generate -i  ../petstore-expanded.yaml -g asciidoc -o temp/asciidoc

    npx @openapitools/openapi-generator-cli generate -i  ../petstore-expanded.yaml -g markdown -o temp/markdown

### not working or looking good

    dynamic-html
    html

### Other formats

    npx @openapitools/openapi-generator-cli generate -i  ../petstore-expanded.yaml -g plantuml -o temp/plantuml

    npx @openapitools/openapi-generator-cli generate -i  ../petstore-expanded.yaml -g mysql-schema -o temp/mysql-schema

https://openapi-generator.tech/docs/generators
