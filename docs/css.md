##External standards
1. In class naming we use the BEM standard.
- http://getbem.com/naming/

##Preprocessors
1. We use the Sass preprocessor (Scss) to efficiently create CSS stylesheets:
- http://sass-lang.com/documentation/file.SASS_REFERENCE.html

##Formatting the stylesheet and correct use of selector properties and values
1. Classes should not describe content, should be appropriate for the element.
For example, in the case of the \<img\> tag containing a picture of a man, we do not give him the "men" class.
We can extend it to a class that corresponds to specific properties

2. Tabulator 4 spaces.

3. We do not use "important". If we used, we leave a comment for another developer for what purpose we did.

4. Colors are saved in HEX format, in case of transparency we can use RGBA. We do not use verbal values ​​such as "white".

5. Media queries for a particular class are declared as close as possible to this class and not to a separate stylesheet.

6. We do not give the minus sign "-" for the value 0. We also do not give units. 0 can not be negative or have units.

7. We group similar properties automatically or manually.

Example:  

Incorrect:
```css
.box{
    position: absolute;
    top: 0;
    padding: 12px;
    left: -20px;
    margin: 0;
}
```

Correct:
```css
.box{
    position: absolute;
    top: 0;
    left: -20px;
    margin: 0;
    padding: 12px;
}
```

8. The "id" attribute must have a unique value within the document, and we do not use it as a class (we do not give it a property).

9. Repeated properties for several elements are written in separate classes.

10. In stylesheets, we use single quotation marks instead of double quotes.

11. The last property of the selector also ends with a semicolon ";".

12. We try not to nest classes (BEM).

13. Each property written from the new line.

14. Animations are declared at the end of the stylesheets.

15. We use aggregate properties.

Example:
Incorrect:
```css
.box{
    margin-top: 12px;
    margin-right: 20px;
    margin-bottom: 20px;
    margin-left: 0;
}
```

Correct:
```css
.box{
    margin: 12px 20px 20px 0;
}
```

16. We try to use the lowest values ​​for the "z-index" property. For example, if we have one main template layer and modal, we can limit ourselves to 5 for modal. We do not give him 999999 right away, later it may be hard to throw something above.

## Sass (Scss)

1. Variable files start from the floor so they are not compiled into separate css files. Correct example: _variables.scss

2. Repeating values ​​such as colors, shadows, borders, rounded corners, transitions - write to variables.

3. For similar items we create classes that we extend to other classes through "@extend".