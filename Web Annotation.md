
# Spring Web Annotations

### @Controller
- **Description**: Marks a class as a Spring MVC controller.
- **Usage**:

```java
@Controller
public class MyController {

    @RequestMapping("/home")
    public String home() {
        return "home";
    }
}
```

### @RestController
- **Description**: A combination of `@Controller` and `@ResponseBody`. It is used for RESTful web services.
- **Usage**:

```java
@RestController
public class MyRestController {

    @GetMapping("/api/data")
    public String getData() {
        return "data";
    }
}
```

### @RequestMapping
- **Description**: Used to map web requests to specific handler methods or classes.
- **Usage**:

```java
@Controller
@RequestMapping("/api")
public class MyApiController {

    @RequestMapping("/items")
    public String getItems() {
        return "items";
    }
}
```

### @GetMapping
- **Description**: A shortcut for `@RequestMapping` for GET requests.
- **Usage**:

```java
@RestController
public class MyGetController {

    @GetMapping("/items")
    public List<Item> getItems() {
        return itemService.getItems();
    }
}
```

### @PostMapping
- **Description**: A shortcut for `@RequestMapping` for POST requests.
- **Usage**:

```java
@RestController
public class MyPostController {

    @PostMapping("/items")
    public void addItem(@RequestBody Item item) {
        itemService.addItem(item);
    }
}
```

### @PutMapping
- **Description**: A shortcut for `@RequestMapping` for PUT requests.
- **Usage**:

```java
@RestController
public class MyPutController {

    @PutMapping("/items/{id}")
    public void updateItem(@PathVariable String id, @RequestBody Item item) {
        itemService.updateItem(id, item);
    }
}
```

### @DeleteMapping
- **Description**: A shortcut for `@RequestMapping` for DELETE requests.
- **Usage**:

```java
@RestController
public class MyDeleteController {

    @DeleteMapping("/items/{id}")
    public void deleteItem(@PathVariable String id) {
        itemService.deleteItem(id);
    }
}
```

### @PathVariable
- **Description**: Used to extract values from the URI.
- **Usage**:

```java
@RestController
public class MyPathVariableController {

    @GetMapping("/items/{id}")
    public Item getItem(@PathVariable String id) {
        return itemService.getItem(id);
    }
}
```

### @RequestParam
- **Description**: Used to extract query parameters from the URL.
- **Usage**:

```java
@RestController
public class MyRequestParamController {

    @GetMapping("/search")
    public List<Item> searchItems(@RequestParam String keyword) {
        return itemService.searchItems(keyword);
    }
}
```

### @RequestBody
- **Description**: Used to map the body of an HTTP request to a method parameter.
- **Usage**:

```java
@RestController
public class MyRequestBodyController {

    @PostMapping("/items")
    public void createItem(@RequestBody Item item) {
        itemService.createItem(item);
    }
}
```

### @ResponseBody
- **Description**: Indicates that the return value of a method should be bound to the web response body.
- **Usage**:

```java
@Controller
public class MyResponseBodyController {

    @RequestMapping("/data")
    @ResponseBody
    public String getData() {
        return "This is data";
    }
}
```
