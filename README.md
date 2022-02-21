# E-commerce Back End 

take a working Express.js API and configure it to use Sequelize to interact with a MySQL database.

AS A manager at an internet retail company
I WANT a back end for my e-commerce website that uses the latest technologies
SO THAT my company can compete with other e-commerce companies


GIVEN a functional Express.js API
WHEN I add my database name, MySQL username, and MySQL password to an environment variable file
THEN I am able to connect to a database using Sequelize
WHEN I enter schema and seed commands
THEN a development database is created and is seeded with test data
WHEN I enter the command to invoke the application
THEN my server is started and the Sequelize models are synced to the MySQL database
WHEN I open API GET routes in Insomnia for categories, products, or tags
THEN the data for each of these routes is displayed in a formatted JSON
WHEN I test API POST, PUT, and DELETE routes in Insomnia
THEN I am able to successfully create, update, and delete data in my database

# Category Model
* id: integer, doesn't allow null values, set as pimary key, uses auto increment
* category_name: string, doesn't allow null values

# Product Model 
* id: integer, doesn't allow null values, set as pimary key, uses auto increment
* product_name: string, doesn't allow null values
* price: decimal, not null values, validates that the value is a decimal
* stock: integer, doesn't allow null, set value of 10, validates the value is a true number
* category_id: integer, references category model id

# Tag
* id: integer, doesn't allow null values, set as pimary key, uses auto increment
* tag_name: string

# ProductTag
* id: integer, doesn't allow null values, set as pimary key, uses auto increment
* product_id integer, references product models id
* tag-id: integer, references tag model's id

# Associations
* Product belongs to Category, as a category can have multiple products but a product can only belong to one category.
* Category has many Product models.
* Product belongs to many Tag models. Using the ProductTag through model, allow products to have multiple tags and tags to have many products.
* Tag belongs to many Product models.