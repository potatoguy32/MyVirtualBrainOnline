The relational model is an approach to managing data using a structure and language consistent with first-order predicate logic, first described in 1969 by English computer scientist Edgar F. Codd, where all data is represented in terms of tuples, and grouped into relations.
Opposite data modeling techniques to [[Dimensional Modeling]] where relational model usually applied on the [[OLTP]] database and dimensional on [[OLAP]] or other analytics close solutions. It’s the theoretical foundation of Relational Databases.

## Key terms
- Relation: Equivalent to a table, set of tuples with the same attributes.
- Tuple: A single row in a table, representing a single item or entity.
- Attribute: Corresponds to a column in a table, with a specific data type.
- Domain: Set of all possible values an attribute can have.
- Primary key: A unique identifier for each tuple in a relation. No duplicated values allowed.
- Foreign key: An attribute that links tow tables, referring to the primary key in another table.
- Schema: The formal description of database's structure, including tables, fields, relationships, views and indexes.
- Cardinality: Number of elements in a set, or the number of tuples in a relation.
- Degree: Number of attributes in a relation.
- Integrity constrains: Rules to ensure accuracy and consistency of data across the database.
- View: A virtual table based on the result set of a query. Does not physically store data.

## Use cases
- Relationships and structure in data is clear and consistent. 
- Constraints at relation level.
- Data structure is not constantly changing.

## Translation layer (ORM)
When working with relational models with [[Object Oriented Programming]], an Object Relational Mapper ([[ORM]]) will be used to translate between databases relations and objects in the programming environment.