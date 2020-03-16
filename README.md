# Rails API Quiz

**Using whatever resources you like (e.g., Google, Stack Overflow, lectures, labs, notes, etc.), answer the following questions.**

1. Write the command to create a new Rails application in API mode with a Postgresql database.

```
rails new my-new-rails-api --api --database=postgresql
```

2. What are 5 other options that can be passed in to the `rails new` command and what do they do?

```
--skip-gemfile: don't create a Gemfile
-f: overwrite files that already exist (f stands for force)
-G: skip .gitignore file
-M: skip action mailer files
-O: skip Active Record files
```

3. What one line of code can be put into `routes.rb` to get all the RESTful routes for a given resource (e.g., dogs)?

```
resources :dogs
```

4. In the context of API development, what is versioning? How do we implement versioning in a Rails API?

```
When creating the new rails file, use namespace (::) to nest your version (ie api::v1::dogs).
Different versions may use different routes, so it's important to keep legacy versions up in case
people are still using them.
```

5. What is serialization in reference to a Rails API?

```
Serialization is filtering results of a pull to show or hide certain attributes. For instance, you may
want to see the Bird that owns a Sighting when searching for that Sighting, so you'd have to include
the Bird attribute. Serializing standardizes this method so you always get the same info??
```

6. Imagine a dog walking domain in which a walker has many dogs. Write the `index` action from the `WalkersController`. Remember, your endpoint should return JSON.

```
def index
    walkers = Walker.all

    return json: walkers
end
```

7. Change the code from the question above so that the walkers' dogs get embedded in the JSON being returned from the `index` endpoint.

```
def index
    walkers = Walker.all

    return json: walkers, include: dogs
end
```

8. Again, change the code above to exclude the timestamps from the data being returned in the JSON.

```
def index
    walkers = Walker.all

    return json: walkers, include: dogs, except: [:timestamps]
end
```

9. What does CORS mean? Why do we have to think about it when making an API?

```
CORS stands for cross-origin resource sharing. It restricts requests from outside users on a domain.
```

10. What changes do we have to make in our application to allow CORS?

```

```

11. In our dog walking app, what needs to be added to the following class to allow method calls like `Dog.create(name: "Neikko", breed: "mostly rat", age: 13)` and `Dog.find_by(name: "Neikko")` to function properly?

```
class Dog < ApplicationRecord
    
end
```

```
```




