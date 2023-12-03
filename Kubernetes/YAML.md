# YAML
- YAML stands for yet another markup language.
- It's a human-readable data serialization format often used in configuration files and data exchange due to its simplicity and readability.

- Example:
```yaml
# Comments start with a hash symbol
name: John Doe
age: 30
occupation: Developer
hobbies:
  - Reading
  - Hiking
  - Coding
address:
  street: 123 Main St
  city: Anytown
  zip: 12345

```
## Data Types: YAML supports various data types:
- Scalars: Strings, numbers, booleans, null values.
- Collections: Lists (arrays) and dictionaries (maps/objects)

### Lists (Arrays):
- Lists are ordered collections indicated by a hyphen followed by space for each item.
```yaml
fruits:
  - Apple
  - Banana
  - Orange
```

### Dictionaries (Maps/Objects):
- Dictionaries are key-value pairs where keys map to values.
```yaml
person:
  name: Alice
  age: 25
  address:
    street: 456 Elm St
    city: Somewhere
```
