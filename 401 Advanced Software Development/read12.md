#  Spring RESTful Routing & Static Files

- @Entity are used to annotated classes.
- The object id property is annotated with @Id
- The id property is also annotated with @GeneratedValue
- Spring Data JPA focuses on using JPA to store data in a relational database.Its most compelling feature is the ability to create repository implementations automatically, at runtime, from a repository interface.

### Example:

> package com.example.accessingdatajpa;
> import java.util.List;
import org.springframework.data.repository.CrudRepository;
public interface CustomerRepository extends CrudRepository <Customer, Long> {
List <Customer> findByLastName(String lastName);
Customer findById(long id); }

- Spring Data JPA also lets you define other query methods by declaring their method signature.

>For example, CustomerRepository includes the findByLastName() method.

-**CrudRepository** provides CRUD functions

- **PagingAndSortingRepository** provides methods to do pagination and sort records
- **JpaRepository** provides JPA related methods such as flushing the persistence context and delete records in a batch

**NOTE**
-Because of this inheritance relationship, the JpaRepository contains the full API of CrudRepository and PagingAndSortingRepository.

### CRUD Functionality:

1. save(…) – save an Iterable of entities. Here, we can pass multiple objects to save them in a batch
2. findOne(…) – get a single entity based on passed primary key value
3. findAll() – get an Iterable of all available entities in database
4. count() – return the count of total entities in a table
5. delete(…) – delete an entity based on the passed object
6. exists(…) – verify if an entity exists based on the passed primary key value

### JpaRepository

1. findAll() – get a List of all available entities in database
2. findAll(…) – get a List of all available entities and sort them using the provided condition
3. save(…) – save an Iterable of entities. Here, we can pass multiple objects to save them in a batch
4. flush() – flush all pending task to the database
5. saveAndFlush(…) – save the entity and flush changes immediately
6. deleteInBatch(…) – delete an Iterable of entities. Here, we can pass multiple objects to delete them in a batch





## Reference and Citation

> Hambalieu Jallow