# Part Zero - Generator

## Install generator CLI

    npm install @openapitools/openapi-generator-cli -g

https://openapi-generator.tech/docs/installation


https://openapi-generator.tech/docs/generators

## Commnands

https://openapi-generator.tech/docs/usage/

### list

    openapi-generator-cli help list
    NAME
            openapi-generator-cli list - Lists the available generators
    SYNOPSIS
            openapi-generator-cli list [(-i <include> | --include <include>)]
                    [(-s | --short)]
    OPTIONS
            -i <include>, --include <include>
                comma-separated list of stability indexes to include (value:
                all,beta,stable,experimental,deprecated). Excludes deprecated by
                default.
            -s, --short
                shortened output (suitable for scripting)

### config-help

    openapi-generator-cli help config-help
    NAME
            openapi-generator-cli config-help - Config help for chosen lang
    SYNOPSIS
            openapi-generator-cli config-help
                    [(-f <output format> | --format <output format>)] [--feature-set]
                    [--full-details]
                    [(-g <generator name> | --generator-name <generator name>)]
                    [--import-mappings] [--instantiation-types]
                    [--language-specific-primitive] [--markdown-header] [--named-header]
                    [(-o <output location> | --output <output location>)] [--reserved-words]
    OPTIONS
            -f <output format>, --format <output format>
                Write output files in the desired format. Options are 'text',
                'markdown' or 'yamlsample'. Default is 'text'.
            --feature-set
                displays feature set as supported by the generator
            --full-details
                displays CLI options as well as other configs/mappings (implies
                --instantiation-types, --reserved-words,
                --language-specific-primitives, --import-mappings,
                --supporting-files)
            -g <generator name>, --generator-name <generator name>
                generator to get config help for
            --import-mappings
                displays the default import mappings (types and aliases, and what
                imports they will pull into the template)
            --instantiation-types
                displays types used to instantiate simple type/alias names
            --language-specific-primitive
                displays the language specific primitives (types which require no
                additional imports, or which may conflict with user defined model
                names)
            --markdown-header
                When format=markdown, include this option to write out markdown
                headers (e.g. for docusaurus).
            --named-header
                Header includes the generator name, for clarity in output
            -o <output location>, --output <output location>
                Optionally write help to this location, otherwise default is
                standard output
            --reserved-words
                displays the reserved words which may result in renamed model or
                property names

#### generate

openapi-generator-cli help generate
NAME
        openapi-generator-cli generate - Generate code with the specified
        generator.
SYNOPSIS
        openapi-generator-cli generate
                [(-a <authorization> | --auth <authorization>)]
                [--api-name-suffix <api name suffix>] [--api-package <api package>]
                [--artifact-id <artifact id>] [--artifact-version <artifact version>]
                [(-c <configuration file> | --config <configuration file>)] [--dry-run]
                [(-e <templating engine> | --engine <templating engine>)]
                [--enable-post-process-file]
                [(-g <generator name> | --generator-name <generator name>)]
                [--generate-alias-as-model] [--git-host <git host>]
                [--git-repo-id <git repo id>] [--git-user-id <git user id>]
                [--global-property <global properties>...] [--group-id <group id>]
                [--http-user-agent <http user agent>]
                [(-i <spec file> | --input-spec <spec file>)]
                [--ignore-file-override <ignore file override location>]
                [--import-mappings <import mappings>...]
                [--instantiation-types <instantiation types>...]
                [--invoker-package <invoker package>]
                [--language-specific-primitives <language specific primitives>...]
                [--legacy-discriminator-behavior] [--library <library>]
                [--log-to-stderr] [--minimal-update]
                [--model-name-prefix <model name prefix>]
                [--model-name-suffix <model name suffix>]
                [--model-package <model package>]
                [(-o <output directory> | --output <output directory>)] [(-p <additional properties> | --additional-properties <additional properties>)...]
                [--package-name <package name>] [--release-note <release note>]
                [--remove-operation-id-prefix]
                [--reserved-words-mappings <reserved word mappings>...]
                [(-s | --skip-overwrite)] [--server-variables <server variables>...]
                [--skip-operation-example] [--skip-validate-spec]
                [--strict-spec <true/false strict behavior>]
                [(-t <template directory> | --template-dir <template directory>)]
                [--type-mappings <type mappings>...] [(-v | --verbose)]

## Generator examples

### Spring

CLI

    openapi-generator-cli generate -g spring -o temp/spring  -i ../petstore.yaml

    option -c for configuration file e.g. openapitools-config-spring.json is optional

Maven example

    cd spring-boot-example
    mvn clean compile

https://openapi-generator.tech/docs/generators/spring

https://openapi-generator.tech/docs/plugins/

https://github.com/OpenAPITools/openapi-generator/tree/master/modules/openapi-generator-maven-plugin
