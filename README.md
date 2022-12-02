## What Is This?

This is an example repo corresponding to multiple lessons within the LearnHowToProgram.com walkthrough on creating a To Do List application in [Section 4: Many-to-Many Relationships](https://www.learnhowtoprogram.com/c-and-net/many-to-many-relationships).

This project corresponds to the classwork and lessons that describe how to connect an ASP.NET Core MVC project to a MySQL database using [Entity Framework Core](https://learn.microsoft.com/en-us/ef/core/) with migrations. This project contains a one-to-many relationship between `Item` and `Category`, and a many-to-many relationship between `Item` and `Tag`. There are multiple lessons in this series. The first lesson in the series is [Code First Development and Migrations](https://www.learnhowtoprogram.com/c-and-net-part-time/many-to-many-relationships/code-first-development-and-migrations).

There are multiple branches in this repo that are described more below.

## How To Run This Project

### Install Tools

Install the tools that are introduced in [this series of lessons on LearnHowToProgram.com](https://www.learnhowtoprogram.com/c-and-net/getting-started-with-c).

### Set Up and Run Project

1. Clone this repo.
2. Open the terminal and navigate to this project's production directory called "ToDoList".
3. Within the production directory "ToDoList", create a new file called `appsettings.json`.
4. Within `appsettings.json`, put in the following code, replacing the `uid` and `pwd` values with your own username and password for MySQL. For the LearnHowToProgram.com lessons, we always assume the `uid` is `root` and the `pwd` is `epicodus`.

```json
{
  "ConnectionStrings": {
      "DefaultConnection": "Server=localhost;Port=3306;database=to_do_list_with_many_to_many;uid=root;pwd=epicodus;"
  }
}
```

5. Create the database using the migrations in the To Do List project. Open your shell (e.g., Terminal or GitBash) to the production directory "ToDoList", and run `dotnet ef database update`. 
    - To optionally create a migration, run the command `dotnet ef migrations add MigrationName` where `MigrationName` is your custom name for the migration in UpperCamelCase. To learn more about migrations, visit the LHTP lesson [Code First Development and Migrations](https://www.learnhowtoprogram.com/c-and-net-part-time/many-to-many-relationships/code-first-development-and-migrations).
6. Within the production directory "ToDoList", run `dotnet watch run` in the command line to start the project in development mode with a watcher.
4. Open the browser to _https://localhost:5001_. If you cannot access localhost:5001 it is likely because you have not configured a .NET developer security certificate for HTTPS. To learn about this, review this lesson: [Redirecting to HTTPS and Issuing a Security Certificate](https://www.learnhowtoprogram.com/lessons/redirecting-to-https-and-issuing-a-security-certificate).


## Available Branches

**1_starter_project**: This is the default branch with the starter code for the To Do List project as an ASP.NET Core MVC web application that is configured to use Entity Framework Core to communicate with a MySQL database as completed at the end of section 3. **This branch is not meant to be run using the above instructions, as it is not configured to use EF Core migrations; instead it is meant to be used as a starting point for the refactor we begin in the LHTP lesson [Code First Development and Migrations](https://www.learnhowtoprogram.com/c-and-net-part-time/many-to-many-relationships/code-first-development-and-migrations).**

**2_many_to_many_setup**: This branch includes the code we added after working through the following lessons:

- https://www.learnhowtoprogram.com/c-and-net/many-to-many-relationships/code-first-development-and-migrations
- https://www.learnhowtoprogram.com/c-and-net/many-to-many-relationships/many-to-many-relationships-join-entities

**3_m2m_read_and_create**: This branch includes the code we added after working through the following lessons:

- https://www.learnhowtoprogram.com/c-and-net/many-to-many-relationships/many-to-many-read-functionality
- https://www.learnhowtoprogram.com/c-and-net/many-to-many-relationships/many-to-many-create-functionality

**4_m2m_update_and_delete**: This branch includes the code we added after working through the following lessons:

- https://www.learnhowtoprogram.com/c-and-net/many-to-many-relationships/many-to-many-update-functionality
- https://www.learnhowtoprogram.com/c-and-net/many-to-many-relationships/many-to-many-delete-functionality

**5_model_validation**: This branch includes the code we added after working through the following lesson:

- https://www.learnhowtoprogram.com/c-and-net/many-to-many-relationships/model-validation-with-validation-attributes

**6_data_from_multiple_db_tables**: This branch includes the code we added after working through the following lesson:

- https://www.learnhowtoprogram.com/c-and-net/many-to-many-relationships/creating-a-splash-page-with-data-from-multiple-database-tables