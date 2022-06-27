## Save data in the local database

- The ability to cache data will help when there is no network and still wors offline
- database class
- data entities
- data access objects

- The following we are setting up our database

```Java
@Entity
public class User {
    @PrimaryKey
    public int uid;

    @ColumnInfo(name = "first_name")
    public String firstName;

    @ColumnInfo(name = "last_name")
    public String lastName;
}

```

- [Credit](https://developer.android.com/training/data-storage/room)
- Use the `@ColkumnInfo` for the data entity

- The follwoing we need to access our database

```Java
@Dao
public interface UserDao {
    @Query("SELECT * FROM user")
    List<User> getAll();

    @Query("SELECT * FROM user WHERE uid IN (:userIds)")
    List<User> loadAllByIds(int[] userIds);

    @Query("SELECT * FROM user WHERE first_name LIKE :first AND " +
           "last_name LIKE :last LIMIT 1")
    User findByName(String first, String last);

    @Insert
    void insertAll(User... users);

    @Delete
    void delete(User user);
}
```

- [Credit](https://developer.android.com/training/data-storage/room)

- Then we need to set up an AppDatabase class to hold the database
- then we need to creat an instance of the database
- Then we need to use the abstrat methods from our database access object

## Defining data using Room entities

- In our example above creating the entity class there are many ways we can manbipulate our
  table in our database through the entity

- The following example displays the different annontations that can be used for primary keys, ignore fields, and pivot table search support

```Java
// Use `@Fts3` only if your app has strict disk space requirements or if you
// require compatibility with an older SQLite version.
@Fts4
@Entity(tableName = "users")
public class User {
    // Specifying a primary key for an FTS-table-backed entity is optional, but
    // if you include one, it must use this type and column name.
    @PrimaryKey
    @ColumnInfo(name = "rowid")
    public int id;

    @ColumnInfo(name = "first_name")
    public String firstName;
}
```

- [Credit](https://developer.android.com/training/data-storage/room/defining-data)

- You can also add AutoValue using `@AutoValue` and `@CopyAnnotations`

## Define relationships between objects

-Room forbids entities referencing each other

- You can make an intermediate4 data class
- You can slo use Multimap Return Types

```Java
@Query(
    "SELECT * FROM user" +
    "JOIN book ON user.id = book.user_id"
)
public Map<User, List<Book>> loadUserAndBookNames();

```

- [Credit](https://developer.android.com/training/data-storage/room/relationships)

- @Embedded Allows you to decompose into subfields in a table

### One to One Relationship

```Java
@Entity
public class User {
    @PrimaryKey public long userId;
    public String name;
    public int age;
}

@Entity
public class Library {
    @PrimaryKey public long libraryId;
    public long userOwnerId;

    ////////////////////////////////
    public class UserAndLibrary {
        @Embedded public User user;
        @Relation(
                parentColumn = "userId",
                entityColumn = "userOwnerId"
        )
        public Library library;
    }
}

////////////////////////////////

    @Transaction
    @Query("SELECT * FROM User")
    public List<UserAndLibrary> getUsersAndLibraries();
```

- [Credit](https://developer.android.com/training/data-storage/room/relationships)

### Details on other relationships

- In the Relation class for One to Many call with `ObjectWithObject`
- `@Junction` is used in the many to many relationship
- If you are doing an nested relationship use @Embedded

## Accessing data using Room DAOs

- DAO can be an abstract class or implementation
- In a DAO you define the database interactions
- convenience annotations are used for defining methods ` @Insert public void insertUsersAndFriends(User user, List<User> friends);`
- Use the following for CRUD actiosn
- `@Update`
- `@Delete`
- You can set up queries using `@Query` You can also grrom or streamline with subsets in the columns
- Basically you can manipulate what you want in by inserting specific SQL into your `@Query`
- Example: `@Query( "SELECT * FROM user" + "JOIN book ON user.id = book.user_id" + "GROUP BY user.name WHERE COUNT(book.id) >= 3" )`




> ## Reference and Citation

> Joshua McCluskey
