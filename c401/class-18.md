# Read: 18 - Web App Security

## [Many to many relationships](https://www.baeldung.com/hibernate-many-to-many/)

**_quick look at how the `@ManyToMany` annotation can be used for specifying this type of relationships in Hibernate._**

### A Typical Example

- simple Entity Relationship Diagram – which shows the many-to-many association between two entities employee and project
- any given employee can be assigned to multiple projects and a project may have multiple employees working for it
![many-to-many](https://www.baeldung.com/wp-content/uploads/2017/09/New.png)

1. created database with the name for the example : `spring_hibernate_many_to_many`

1. create the employee and project tables along with the `employee_project` join table with `employee_id` and `project_id` as foreign keys

1. Once that is setup, preparation of the Maven dependencies and Hibernate configuration needs to be done.

1. Create model classes with JPA annotations. When both classes refer to one another, the association between them is bidirectional.

1. In order to map a many-to-many association, we use the `@ManyToMany`, `@JoinTable` and `@JoinColumn` annotations.

   -  `@ManyToMany` annotation is used in both classes to create the many-to-many relationship between the entities. This association has two sides i.e. the owning side and the inverse side.
   -  `@JoinTable` is used to define the join/link table.
   -  `@JoinColumn` annotation is used to specify the join/linking column with the main table.

## [Security: a humorous overview](https://scholar.harvard.edu/files/mickens/files/thisworldofours.pdf)

- Funny overview about security and security researchers and some stories from the real life.