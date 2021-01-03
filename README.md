# dotnet-with-auth-template
This is a somewhat opinionated template I use to quickstart a Dotnet 5 API with auth (individual user auth using JWTs). It's setup using Postgres but can be easily swapped with another db.

If you clone it, setup a database, update connection strings in the appsettings files, you will end up with a fully functioning Dotnet 5 web api with auth already taken care of (sign up and login routes are done already).

### Deploy to Azure (free)
Run this command after creating an Azure account (and installing the azure commandline tools and run `az login`) and it'll put this app into azure for free. Run the same command to update the app after you have made some changes.
```
az webapp up --sku F1 --name test-app-caleb --os-type linux
```

If your app uses a database (which it needs for authentication) you'll need to host the db somewhere and setup the connection string in the appsettings files. See below for free postgres hosting.


### Database commands reference
When you setup your database, update the connection strings you should be able to run this command which will run the db migrations against your database and create all the tables needed (for auth etc):
Run migrations: `dotnet ef database update`

### Free postgres db: https://api.elephantsql.com