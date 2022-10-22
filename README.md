# rest-api
Pluget REST-API

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
