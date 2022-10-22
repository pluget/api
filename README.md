# rest-api
Pluget REST-API

## Specification
The spefication is developed in the openapi format and can be found inside the `pluget.yaml` file.
You can also edit it more conveniently over an GUI by uploading it to
[https://mermade.github.io/openapi-gui/#](https://mermade.github.io/openapi-gui/#).

## Client libraries
You can generate a fully featured client library 
for basically any programming language with the help of [openapi-generator](https://github.com/OpenAPITools/openapi-generator#3---usage).
Its easy as well, like shown below (generates C#/csharp client library):
1. Download the openapi-generator-cli.jar from [here](https://github.com/OpenAPITools/openapi-generator#13---download-jar).
2. Execute this command: `java -jar openapi-generator-cli.jar generate -i https://raw.githubusercontent.com/pluget/rest-api/main/pluget.yaml -g csharp -o openapi-generated/client/pluget/csharp` (for all supported languages see [here](https://openapi-generator.tech/docs/generators/)). 
3. Copy the generated code into your project.

### Design (API endpoints)

#### https://api.pluget.net/v1
- Description: The main url to access the REST-API.

#### /all
- Description: Returns all the data (name, data, versions). One page could show a maximum of 20 plugins.
- Example: https://api.pluget.net/v1/all?pageID=0&pluginsShown=5
- Optional params: pageID (default 0), pluginsShown (max 20, default 10)

#### /names
- Description: Retuns all names.
- Example: https://api.pluget.net/v1/names?pageID=0&pluginsShown=5
- Optional params: pageID (default 0), pluginsShown (max 4294967295, default 1000)

#### /data
- Description: Returns all the plugins data (without versions). 
- Example: https://api.pluget.net/v1/data?pageID=0&pluginsShown=5
- Optional params: pageID (default 0), pluginsShown (max 20, default 10)

#### /versions
- Description: Return all the plugins versions (without data).
- Example: https://api.pluget.net/v1/versions?pageID=0&pluginsShown=5
- Optional params: pageID (default 0), pluginsShown (max 20, default 10)

#### /find
- Description: Returns an array containing only the objects that match the query.
- Examples:
  - https://api.pluget.net/v1/find?author=queryString 
  - https://api.pluget.net/v1/find?name=queryString
  - https://api.pluget.net/v1/find?pgid=queryString
  - https://api.pluget.net/v1/find?name=queryString&author=queryString
- Required params (at least one): author, name, pgid

## Contributing

Contributors are welcome, please fork and send pull requests! If you find a bug
or have any ideas on how to improve this project please submit an issue.
