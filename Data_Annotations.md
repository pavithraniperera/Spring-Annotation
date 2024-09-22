
# Data Annotations in Spring

## 1. @Entity
**Description:**  
Marks a class as a JPA entity that is mapped to a database table.

**Sample Code:**
```java
@Entity
public class User {
    @Id
    private Long id;
    private String name;
    private String email;
}
```

## 2. @Table
**Description:**  
Specifies the name of the database table to which an entity should be mapped.

**Sample Code:**
```java
@Entity
@Table(name = "users")
public class User {
    @Id
    private Long id;
    private String name;
    private String email;
}
```

## 3. @Id
**Description:**  
Marks a field as the primary key of the entity.

**Sample Code:**
```java
@Entity
public class User {
    @Id
    private Long id;
}
```

## 4. @GeneratedValue
**Description:**  
Specifies the strategy for generating primary key values (e.g., `AUTO`, `IDENTITY`, etc.).

**Sample Code:**
```java
@Entity
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
}
```

## 5. @Column
**Description:**  
Specifies the details of the column in the database for the mapped entity field.

**Sample Code:**
```java
@Entity
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(name = "user_name", nullable = false)
    private String name;
}
```

## 6. @OneToMany
**Description:**  
Defines a one-to-many relationship between two entities.

**Sample Code:**
```java
@Entity
public class User {
    @OneToMany(mappedBy = "user")
    private List<Order> orders;
}
```

## 7. @ManyToOne
**Description:**  
Defines a many-to-one relationship between two entities.

**Sample Code:**
```java
@Entity
public class Order {
    @ManyToOne
    @JoinColumn(name = "user_id")
    private User user;
}
```

## 8. @JoinColumn
**Description:**  
Specifies the column used for joining an entity association.

**Sample Code:**
```java
@Entity
public class Order {
    @ManyToOne
    @JoinColumn(name = "user_id")
    private User user;
}
```

## 9. @Transient
**Description:**  
Indicates that a field should not be persisted to the database.

**Sample Code:**
```java
@Entity
public class User {
    @Transient
    private int age;
}
```

## 10. @Embedded
**Description:**  
Embeds another entity inside this entity.

**Sample Code:**
```java
@Entity
public class Address {
    private String city;
    private String state;
}

@Entity
public class User {
    @Embedded
    private Address address;
}
```

## 11. @Embeddable
**Description:**  
Marks a class as embeddable within other entities.

**Sample Code:**
```java
@Embeddable
public class Address {
    private String city;
    private String state;
}
```
