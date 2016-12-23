# Deploy in meteor

## Manually

### Links
- https://guide.meteor.com/deployment.html
- https://nodejs.org/en/
- https://www.meteor.com/
- https://www.mongodb.com/

### Pre requirements
- MongoDB
- NodeJS
- Meteor

### Create database
- Access mongo server, using _cli_ mongo
```
mongo
```
- **Create** the _database_
```
use dataBaseName
```
- **Create** the _user_ for your database
```
db.createUser(
  {
    user: "userName",
    pwd: "userPassword",
    roles: [ { role: "userAdminAnyDatabase", db: "admin" } ]
  }
);
```

### Building
- Rode o comando abaixo para gerar o build de acordo com a **arquitetura** que deseja
    - Para saber quais os tipos de arqitetura consulte a documentação do meteor 
```
npm install --production
meteor build **/destinoDesejado** --architeture os.linux.x86_34 
```
- Extract file(normally called **bundle**.tar)
- Go to folder created after extract
```
cd bundle/programs/server                           
```
- Install dependencies
```
npm install
```
- Back in main folder **bundle**
```
cd ../../
```
- Execute the command for init the project, define the _URLS_:
    - **MONGO_URL** define url _database_
    - **ROOT_URL** define url for _project_ access
    - **PORT** define the _port_
```
MONGO_URL=mongodb://_databaseUser_:_databasePassword_@_databaseServer_:_portServer_/_databaseName_ ROOT_URL=http://my-app.com PORT=_porta_ nohup node main.js &
```

### Observations
- Case any error in  _init_ the server, Saying that the environment variables are not defined (**MONGO_URL, ROOT_URL, PORT**), use the commands.
```
export VARIAVEL_ENVIRONMENT = VALUE
```
