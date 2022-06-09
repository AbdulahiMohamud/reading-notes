# Web App Security

### Many to Many Annotation

- The ```@ManyToMany``` annotation is used in both classes to create the many-to-many relationship between the entities.  

- Example of a **many-to-many** relation can be In this scenario, any given employee can be assigned to multiple projects and a project may have multiple employees working for it, leading to a many-to-many association between the two.

- With a many-to-many we have an employee table with **employee_id** as its primary key and a project table with **project_id** as its primary key.A join table **employee_project** is required to connect both sides.

### Database Setup

```
CREATE TABLE `employee` (
`employee_id` int(11) NOT NULL AUTO_INCREMENT,
`first_name` varchar(50) DEFAULT NULL,
`last_name` varchar(50) DEFAULT NULL,
PRIMARY KEY (`employee_id`)
) ENGINE=InnoDB AUTO_INCREMENT=17 DEFAULT CHARSET=utf8;

CREATE TABLE `project` (
`project_id` int(11) NOT NULL AUTO_INCREMENT,
`title` varchar(50) DEFAULT NULL,
PRIMARY KEY (`project_id`)
) ENGINE=InnoDB AUTO_INCREMENT=18 DEFAULT CHARSET=utf8;

CREATE TABLE `employee_project` (
`employee_id` int(11) NOT NULL,
`project_id` int(11) NOT NULL,
PRIMARY KEY (`employee_id`,`project_id`),
KEY `project_id` (`project_id`),
CONSTRAINT `employee_project_ibfk_1`
FOREIGN KEY (`employee_id`) REFERENCES `employee` (`employee_id`),
CONSTRAINT `employee_project_ibfk_2`
FOREIGN KEY (`project_id`) REFERENCES `project` (`project_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
```

### The Model Classes

- The model classes Employee and Project need to be created with JPA annotations:

```
@Entity
@Table(name = "Employee")
public class Employee { 
    // ...
 
    @ManyToMany(cascade = { CascadeType.ALL })
    @JoinTable(
        name = "Employee_Project", 
        joinColumns = { @JoinColumn(name = "employee_id") }, 
        inverseJoinColumns = { @JoinColumn(name = "project_id") }
    )
    Set<Project> projects = new HashSet<>();
   
    // standard constructor/getters/setters
}
@Entity
@Table(name = "Project")
public class Project {    
    // ...  
 
    @ManyToMany(mappedBy = "projects")
    private Set<Employee> employees = new HashSet<>();
    
    // standard constructors/getters/setters   
}
```

- As we can see, both the Employee class and Project classes refer to one another, which means that the association between them is bidirectional.

- The ```@ManyToMany``` annotation is used in both classes to create the many-to-many relationship between the entities.

- The owning side is Employee so the join table is specified on the owning side by using the ```@JoinTable``` annotation in Employee class.

- The ```@JoinTable``` is used to define the join/link table. In this case, it is *Employee_Project*.

- The ```@JoinColumn``` annotation is used to specify the join/linking column with the main table. Here, the join column is *employee_id* and *project_id* is the inverse join column since Project is on the inverse side of the relationship.

- The *mappedBy* attribute is used in the ```@ManyToMany``` annotation to indicate that the employees collection is mapped by the projects collection of the owner side.  



## Reference and Citation

> Hambalieu Jallow <