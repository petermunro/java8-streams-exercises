# Streams Practice

Work through these practice questions one by one, and study or look up anything you're unsure of.

### Integer Streams

For these questions, assume you have this Integer list available:

```java
List<Integer> intList = Arrays.asList(23, 52, 14, 89, 61, 5, 12, 106, 47, 30);
```

1. Given the above list of integers, produce a stream containing only the even numbers and print them out.

2. Find the maximum value.

3. Calculate the average integer value.

4. Convert a stream of integers back to a List.

5. How do you create an infinite stream of integers starting from 1?

6. How do you limit the number of elements in a Stream to 5?

7. Count the number of elements in the stream of integers.

8. Remove duplicate elements from the stream.

9. Sort the stream of integers in ascending order.

### String Streams

For these questions, assume you have this String list available:

```java
List<String> stringList = Arrays.asList("colony", "colony", "laser", "code", "pay", "pluck", "murder", "anger", "mislead", "tap", "outside", "tap", "outside", "perfume", "crack", "attack", "chorus", "eat");
```

10. Filter out Strings with length less than 6.

11. Concatenate all Strings in the Stream of Strings, and separate them with a comma and a space.

12. Convert the Stream of Strings to a Stream of their lengths.

13. Sort the Stream of Strings lexicographically.

14. Count the number of Strings in a Stream that start with the character "c".

15. Convert the Stream of Strings to an array of Strings.

16. Convert a Stream of Strings to uppercase.

17. Group Strings in a Stream by their length.

18. How do you remove duplicate Strings from a Stream?

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

I've included a `Person` class and some sample data in this repo.

19. Filter a stream of `Person` objects to obtain those with an age greater than 50.

20. Find the oldest person in a Stream of `Person` objects.

21. Calculate the average age of a Stream of Person objects.

22. Sort a Stream of Person objects by name.

23. Count the number of Person objects in a Stream that live in New York.

24. Convert a Stream of Person objects to a List of their names.

25. Similar to Q24, but convert the stream into a list of names by storing it in a `TreeSet`. How does this differ from Q24?

26. Group the Person objects by their city.

27. Investigate the `Collectors.toMap()` method. How would you use this to create a `Map` with the name of a person as the key and the person object as the value?
