# Related Resources and Integration Testing

## One-to-One Relationship

-A one-to-one relationship refers to the relationship between two entities/database tables A and B in which only one element/row of A may only be linked to one element/row of B, and vice versa.

- It is declared by using the *@OneToOne* annotation.

### The @OneToOne accepts the following parameters below

- *fetch* — Defines a strategy for fetching data from the database. By default, it is EAGER which means that the data must be eagerly fetched. We have set it to LAZY to fetch the entities lazily from the database.
- *cascade* — Defines a set of cascadable operations that are applied to the associated entity. CascadeType.ALL means to apply all cascading operations to the related entity. Cascading operations are applied when you delete or update the parent entity.
- *mappedBy* — Defines the entity that owns the relationship which is the **Address** entity in our case.
- *optional* — Defines whether the relationship is optional. If set to false then a non-null relationship must always exist.

#### Notes

-In a bidirectional relationship, we have to specify the @OneToOne annotation in both entities. But only one entity is the owner of the association.

-The **@JoinColumn** annotation is used to specify the foreign key column in the owner of the relationship.

#### The @JoinColumn accepts the following 2 parameters

- **name** — Defines the name of the foreign key column.
- **nullable** — Defines whether the foreign key column is nullable. By default, it is true.

### One-to-Many Relationship

- A one-to-many relationship refers to the relationship between two entities/tables A and B in which one element/row of A may only be linked to many elements/rows of B, but a member of B is linked to only one element/row of A.
- A as a book, and B as pages. A book can have many pages but a page can only exist in one book, forming a one-to-many relationship
- A one-to-many relationship between two entities is defined by using the **@OneToMany** annotation in Spring Data JPA
- It declares the *mappedBy* element to indicate the entity that owns the bidirectional relationship.

### Many-to-Many Relationship

-A many-to-many relationship refers to the relationship between two entities/tables A and B in which one element/row of A may only be associated with many elements/rows of B and vice versa.

- A typical example of such a many-to-many relationship is the relationship between students and courses. A student can enroll in multiple courses and a course can also have multiple students, thus forming a many-to-many relationship.
- We need to create two entity classes, Student and Course, to map the above many-to-many relationship. You don't need to create a separate entity class for the join table.
-Both Student and Course classes are annotated with the Entity annotation to indicate that they are JPA entities.
- A many-to-many relationship between two entities is defined by using the **@ManyToMany** annotation in Spring Data JPA.
- The **@JoinTable** annotation defines the join table between two entities on the owner's side of the relationship.

## Reference and Citation

> Hambalieu Jallow <
