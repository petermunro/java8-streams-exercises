# Streams Practice Answers

### Integer Streams

For these questions, assume you have this Integer list available:

```java
List<Integer> intList = Arrays.asList(23, 52, 14, 89, 61, 5, 12, 106, 47, 30);
```

1. Given the above list of integers, produce a stream containing only the even numbers and print them out.

   > Answer: Use the `filter()` method with a lambda expression to filter. For example:

   ```java
   intList.stream().filter(n -> n % 2 == 0).forEach(System.out::println);
   ```

2. Find the maximum value.

   > Answer: Use the `max()` method along with the `Comparator.naturalOrder()` comparator. Example:

   ```java
   Optional<Integer> max = intList.stream().max(Comparator.naturalOrder());
   ```

3. Calculate the average integer value.

   > Answer: Use the `mapToInt()` and `average()` methods. Example:

   ```java
   OptionalDouble average = intList.stream().mapToInt(Integer::intValue).average();
   ```

4. Convert a stream of integers back to a List.

   > Answer: Use the `collect()` method with Collectors.`toList()` collector. Example:

   ```java
   List<Integer> intList2 = intList.stream().collect(Collectors.toList());
   ```

5. How do you create an infinite stream of integers starting from 1?

   > Answer: Use the `Stream.iterate()` method. Example:

   ```java
   Stream<Integer> infiniteStream = Stream.iterate(1, n -> n + 1);
   ```

6. How do you limit the number of elements in a Stream to 5?

   > Answer: Use the `limit()` method. Example:

   ```java
   Stream<Integer> limitedStream = intList.stream().limit(5);
   ```

7. Count the number of elements in the stream of integers.

   > Answer: Use the `count()` method on `IntStream`. Example:

   ```java
   long count = intList.stream().mapToInt(Integer::intValue).count();
   ```

8. Remove duplicate elements from the stream.

   > Answer: Use the `distinct()` method. Example:

   ```java
   Stream<Integer> distinctStream = intList.stream().distinct();
   ```

9. Sort the stream of integers in ascending order.

   > Answer: Use the sorted() method. Example:

   ```java
   Stream<Integer> sortedStream = stream.sorted();
   ```

### String Streams

For these questions, assume you have this String list available:

```java
List<String> stringList = Arrays.asList("colony", "colony", "laser", "code", "pay", "pluck", "murder", "anger", "mislead", "tap", "outside", "tap", "outside", "perfume", "crack", "attack", "chorus", "eat");
```

10. Filter out Strings with length less than 6.

    > Answer: Use the `filter()` method with a lambda expression to filter out Strings with a certain length:

    ```java
    stringList.stream().filter(s -> s.length() < 6)
    ```

11. Concatenate all Strings in the Stream of Strings, and separate them with a comma and a space.

    > Answer: Use the `collect()` method with `Collectors.joining()` collector. Example:

    ```java
    String concatenated = stringList.stream().collect(Collectors.joining(", "));
    ```

12. Convert the Stream of Strings to a Stream of their lengths.

    > Answer: Use the `map()` method with a lambda expression. Example:

    ```java
    Stream<Integer> lengths = stringList.stream().map(String::length);
    ```

13. Sort the Stream of Strings lexicographically.

    > Answer: Use the sorted() method. Example:

    ```java
    Stream<String> sortedStream = stringList.stream().sorted();
    ```

14. Count the number of Strings in a Stream that start with the character "c".

    > Answer: Use the `filter()` and `count()` methods. For example, to count the number of Strings starting with 'c':

    ```java
    long count = stringList.stream().filter(s -> s.startsWith("c")).count();
    ```

15. Convert the Stream of Strings to an array of Strings.

    > Answer: Use the `toArray()` method with the String[]::new constructor reference. Example:

    ```java
    String[] stringArray = stringList.stream().toArray(String[]::new);
    ```

16. Convert a Stream of Strings to uppercase.

    > Answer: Use the `map()` method with the String::toUpperCase method reference. Example:

    ```java
    Stream<String> uppercasedStream = stringList.stream().map(String::toUpperCase)
    ```

17. Group Strings in a Stream by their length.

    > Answer: Use the `collect()` method with `Collectors.groupingBy()` collector. Example:

    ```java
    Map<Integer, List<String>> groupedByLength = stringList.stream().collect(Collectors.groupingBy(String::length));
    System.out.println(groupedByLength);
    ```

18. How do you remove duplicate Strings from a Stream?

    > Answer: Use the `distinct()` method. Example:

    ```java
    Stream<String> distinctStream = stringList.stream().distinct();
    ```

### Object Streams

Assume the following simple Person class:

```java
public class Person {
    private String name;
    private int age;
    private String city;

    // Constructor, getters, and setters are omitted for brevity
}
```

19. Filter a stream of `Person` objects to obtain those with an age greater than 50.

    > Answer: Use the `filter()` method with a lambda expression. Example:

    ```java
    people.stream().filter(p -> p.getAge() > 50).forEach(System.out::println);
    ```

20. Find the oldest person in a Stream of `Person` objects.

    > Answer: Use the `max()` method along with a lambda expression. Example:

    ```java
    Optional<Person> oldest = people.stream().max(Comparator.comparingInt(Person::getAge));
    ```

21. Calculate the average age of a Stream of Person objects.

    > Answer: Use the `mapToInt()` and `average()` methods:

    ```java
    OptionalDouble averageAge = people.stream().mapToInt(Person::getAge).average();
    ```

22. Sort a Stream of Person objects by name.

    > Answer: Use the sorted() method with a lambda expression. Example:

    ```java
    Stream<Person> sortedByName = people.stream().sorted(Comparator.comparing(Person::getName));
    ```

23. Count the number of Person objects in a Stream that live in New York.

    > Answer: Use the `filter()` and `count()` methods. For example, to count the number of Person objects living in "New York":

    ```java
    long count = people.stream().filter(person -> "New York".equals(person.getCity())).count();
    ```

24. Convert a Stream of Person objects to a List of their names.

    > Answer: Use the `map()` and `collect()` methods. Example:

    ```java
    List<String> names = people.stream().map(Person::getName).collect(Collectors.toList());
    ```

25. Similar to Q24, but convert the stream into a list of names by storing it in a `TreeSet`. How does this differ from Q24?

    > Answer: Use `Collectors.toCollection()` with the `TreeSet::new` constructor reference:

    ```java
    TreeSet<String> treeNames = people.stream().map(Person::getName).collect(Collectors.toCollection(TreeSet::new));
    ```

26. Group the Person objects by their city.

    > Answer: Use the `collect()` method with `Collectors.groupingBy()` collector:

    ```java
    Map<String, List<Person>> peopleByCity = people.stream().collect(Collectors.groupingBy(Person::getCity));
    ```

27. Investigate the `Collectors.toMap()` method. How would you use this to create a `Map` with the name of a person as the key and the person object as the value?

    > Answer: Use the `collect()` method with `Collectors.toMap()` collector. Example:

    ```java
    Map<String, Person> nameToPerson = people.stream().collect(Collectors.toMap(Person::getName, Function.identity()));
    ```
