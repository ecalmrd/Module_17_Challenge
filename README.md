# Matching a URL with Regular Expressions Tutorial

## Summary

Here we will be describing the syntax that is used to match a URL with Regular Expressions. 

The following is the example we will use for our URL regex:  
```/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/```

 The URL regex takes into account of the different ways URL addresses are written such as:

<span>https://</span><span>www</span>.example.com/    
<span>http://</span>subdomain.example.com/path/to/file.html  
<span>www</span>.example.com  
example.com/path/to/file.html   
example.co.uk  
example.com/page?query=string

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)

## Regex Components
URL regex components consists of:  
Anchors  
Quantifiers  
Grouping  
Bracket Expressions  

### Anchors
The anchors that are used for this regex are ```^``` and ```$```. These anchors are what sets the start and end of the string. To specify the beginning of a string, we use the symbol ```^```, and to indicate the end of a string, we use ```$```. When matching a URL using regular expressions, we enclose the entire regex within the ```^``` and ```$``` symbols.

```/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/```

### Grouping and Capturing
A URL contains several sections that would be helpful if we put them into different groups. In order to do that, we use parenthesis to group specific sections. Let's take a look at our URL regex and break them down into 4 groups.

URL regex:
```/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/```  

The first group describes the http section (https): ```(https?:\/\/)```  
The second group describes the domain section (<span>www</span>.youtube): ```([\da-z\.-]+)```  
The third group describes the top level domain section (.com, .edu): ```([a-z\.]{2,6})```  
The fourth group describes the path: ```([\/\w \.-]*)*```  

### Bracket Expressions
Bracket expressions are used to match a single character from a set of characters. In this URL regex, here is how each bracket expressions are used.

```[\da-z\.-]```  
This bracket expression matches a single character that can be any digit (\d), lowercase letter (a-z), period (.), or hyphen (-). The backslash before the "d" (\d) is used to represent any digit character.

```[a-z\.]```  
This bracket expression matches a single character that can be any lowercase letter (a-z) or period (.).

```[\/\w \.-]```  
This bracket expression matches a single character that can be either a forward slash (/), any word character (\w), a space ( ), period (.), or hyphen (-). The backslash before the "w" (\w) represents any word character, which includes all alphabetic characters, digits, and the underscore character.

### Quantifiers
In regular expressions (regex), a quantifier is a symbol that indicates the number of times a preceding character, group, or character class can occur in a matching string. The quantifiers that are used in this URL regex are ```?``` and ```*```. The ```?``` quantifier matches a single occurrence of the preceding character or group. Next, the ```*``` quanitifier matches multiple occurrences of the preceding character or group. Lastly, the URL regex uses the ```{}``` quantifier. The curly brackets allows you to input a range of instance to be identified. For example ```{2}``` would identify 2 or more instances. 

This portion describes the usage of ```?``` in the URL regex: 

```(https?:\/\/)?```

As you can see, this group uses two ```?``` quantifiers. The first ```?``` is looking for either ```http``` or ```https```. This works because the ```?``` is placed right after the ```s``` from the ```https```. The second ```?``` is placed after the closing parenthesis. This is looking at the entire ```http``` or ```https``` expression and indicating that it may or may not include ```http``` or ```https``` since a valid URL can begin with ```www.```.

The next portion describes the usage of ```*``` in the URL regex:

```([\/\w \.-]*)*```

The ```*``` quantifier is used similarily as the ```?``` except the only difference is that the ```*``` makes the the group optional on multiple occurrences since ```*``` is defined as the quantifier to match one or more occurrences of a preceding character or group.  

Lastly, this portion describes the usage of the ```{}``` in the URL regex:

```([a-z\.]{2,6})```

We see that this portion is used in the top level domain (.com) section of the URL. The curly brackets are used to identify between 2 to 6 characters in that section.


### Character Classes

The character classses used are ```\d``` and ```\w```. 

The ```\d``` matches ONLY digit characters between 0 - 9.   
The ```\w``` matches any word character, letters, as well as including digits, and underscores.

In this case we see the ```\d``` used in the second group, the domain section written as: ```([\da-z\.-]+)```. 
The ```\d``` will match any combination of digits in the domain section. Additionally, we have ```a-z\.-``` which will match any lowercase, periods, and hyphens (dashes).

Lastly, in this example, we see ```\w``` used in the fourth group, the path section written as: ```([\/\w \.-]*)```.
the \w character class is used to match any word character, including letters (both uppercase and lowercase), digits, and underscores. It's equivalent to the character class [a-zA-Z0-9_].


## Author
Email: ecalmrd@gmail.com  
GitHub: https://github.com/ecalmrd



