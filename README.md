# Description
# Table of contents
- [Basics](#basics)
    - [Handling Strings](#handling-strings)
    - [Collections](#collections)
- [Conversions](#conversions)
    - [Collections - Array](#collections---array)
- [Specifics](#specifics)
    - [Copy array](#copy-array)
    - [Convert to String](#convert-to-string)

# Basics
## Handling strings
### Selected String methods

Return | Method | Description 
--- |--- | ---
String | `substring(int begin, int end?)` | substring till end-1
boolean | `contains(charSeq)` | match the sequence
String |`join(delimiter, elements...)` | joins given string with all string elements in argument using delimiter
String[] | `split(String regex, int limit?)` | split by regex match till limit
String | `replace(charSeq old, charSeq new)` | replaces all occurrences
int | `indexOf(char/String seq, fromIndex?)` | returns index
String | `valueOf(value)` | converts given type to string

### Selected StringBuilder methods

Return | Method | Description 
--- |--- | ---
StringBuilder | `append(String s)` | append string
StringBuilder | `insert(int offset, String s)` | insert string at specified offset
StringBuilder | `replace(start, end, str)` | replace string from start to end with str
StringBuilder | `delete(start, end)` | delete from start to end
StringBuilder | `reverse()` | reverse
String | `substring(begin, end?)` | return substr

>Note: StringBuffer is synchronized version of StringBuilder.

## Collections
List, Queue, Set

Return | Method | Description 
--- |--- | ---
boolean | `add(E e)` | insert element
boolean | `remove(Obj element)` | delete an element
void | `clear()` | remove all elements
boolean | `contains(Obj element)` | to search element
Iterator | `iterator()` | returns iterator


# Conversions
## Collections - Array
To Array
```java
Foo[] array = list.toArray(new Foo[0]);
//or
Foo[] array = list.stream().toArray(Foo[]::new);
```
To Collection
1. String[], Integer[] to List (from Class)
```java
List<T> list = new ArrayList<T>(Arrays.asList(arrValues));
```
1. int[] to List (from Primitive)
```java
List<Integer> list = new ArrayList<Integer>(intarr.length);
for(int i: intarr) {
    list.add(i);
}
//or
List<Integer> list = Arrays.stream(intarr).boxed().collect(Collections.toList());
```



# Specifics
## Copy array
### arraycopy
When the array memory is already allocated. or want to reuse existing array.
```java
public static void arraycopy(  
    src, int srcPos,dest, int destPos, int length  
) 
```
### Clone
If we create the clone of a single-dimensional array, it creates the deep copy of the Java array. It means, it will copy the actual value. But, if we create the clone of a multidimensional array, it creates the shallow copy of the Java array which means it copies the references.
```java
int carr[]=arr.clone(); 
```

## Convert to string
### valueOf
If object is null returns "null"
```java
String.valueOf(value);
```
### toString() method
If object is null, null pointer exception
```java
myint.toString()
```
