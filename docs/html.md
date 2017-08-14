## Create a new document

1. The main template file starts with a declaration:
```html
<!DOCTYPE html>
```

2. The \<title\> and \<meta charset = "UTF-8"\> tags can not be omitted and must necessarily be added.


3. CSS styles and JS scripts we keep in separate files and declare them in the html document. Styles sheets declare in
the \<head\> tag, and the JS script files before closing the \<body\> tag. We do not place Styles locally
In the \<style\> tag and the scripts in the \<script\> tag.


4. Declaring style sheets CSS and JS scripts in the \<link\> and \<script\> tags do not use the "type" attribute.

Incorrect:

```html
<link type="text/css" rel="stylesheet" href="css/styles.css" />
<script type="text/javascript" src="js/scripts.js"></script>
```

Correct:
```html
<link rel="stylesheet" href="style.css" />
<script src="script.js"></script>
```

4. When using resources from external sources, we download and save them together with the project in the appropriate subdirectory.

5. If we want to use resources from external sources, we first check that these resources have not been before
downloaded and declared in the project. This includes CSS stylesheets, JS scripts, or fonts.

## Formatting the document and correct use of tags

1. All names are written in English. If for a justified reason another language is used, leave a comment with information what the text concerns.

2. Tabulator 4 spaces.

3. We do not close empty tags, example \<br\>, \<hr\>, <\img\> (...)  

Incorrect:

```html
<img src="/something.png" alt="Lorem ipsum"/>
```

Correct:
```html
<img src="/something.png" alt="Lorem ipsum">
```

3. Do rozdzielenia głównych obszarów na stronie korzystamy ze znaczników \<header\>, \<footer\>, \<section\> oraz <\article\> do
pojedynczej treści. Znacznika \<div\> używamy wewnątrz wymienionych znaczników, tam gdzie ze względów logicznych nie jesteśmy w stanie 
wydzielić obszarów za pomocą tych znaczników.

3. We use the \<header\>, \<footer\> and \<section\> tags to separate the main areas of the page and <\article\>
to single content. The tag \<div\> is used inside these tags, where we can not for logical reasons
separate areas with these markers.

4. We do not use the \ <section \> tag to extract a container or format a document. It is semantic only.Incorrect:

```html
<section id="main_section" class="container">
    <div>(...)</div>
</section>
```

Correct:
```html
<section id="main_section">
    <div class="container">
        <div>(...)</div>
    </div>
</section>
```

4. Attribute values ​​are written in double quotation marks.

Incorrect:
```html
<input type='text' name='first_name' value='John'>
```

Correct use:
```html
<input type="text" name="first_name" value="John">
```

5. Empty attributes are placed at the end after the attributes containing the values:

Incorrect:
```html
<input type="text" readonly name="first_name" value="John">
```

Correct:
```html
<input type="text" name="first_name" value="John" readonly>
```

6. Each attribute we write from the new line. At the "data- *" attributes we write at the end.

Example:
```html
<p id="paragraph_1"
   class="paragraph paragraph-red"
   data-something="value">Lorem ipsum dolor sit amet</p>
```

7. We avoid using inline styles. If for a legitimate reason they were applied, each CSS property starts with a newline.

Example:
```html
<p id="paragraph_1"
   class="paragraph"
   style="color: #fff;
          font-size: 12px;"
   data-something="value">Lorem ipsum dolor sit amet</p>
```

8. For the naming of classes we use lowercase. We divide the single words with a hyphen "-".

Incorrect:
```html
<p class="paragraph paragraphRed">Lorem ipsum dolor sit amet</p>
<p class="paragraph paragraph_red">Lorem ipsum dolor sit amet</p>
<p class="paragraph paragraph_Red">Lorem ipsum dolor sit amet</p>
```

Correct:
```html
<p class="paragraph paragraph-red">Lorem ipsum dolor sit amet</p>
```

9. For the naming id we use lowercase. Single words are separated by "_" floor. The ID must be unique within the document.

Incorrect:
```html
<p id="main-paragraph-1">Lorem ipsum dolor sit amet</p>
```

Correct:
```html
<p id="main_paragraph_1">Lorem ipsum dolor sit amet</p>
```

10. We do not use spaces around tags and attribute values, example:

Incorrect:
```html
<p id="first_paragraph"   class=" paragraph pragraph-red ">Lorem ipsum dolor sit amet</p>
< p class = " paragraph pragraph-red " >Lorem ipsum dolor sit amet</p>
```

Correct:
```html
<p id="first_paragraph" class="paragraph pragraph-red">Lorem ipsum dolor sit amet</p>
```

11. We do not use markers to format the document. 
Example we do not use:
- \<br\> to get a margin,
- \<i\> to italic style,
- \<b\> to bold,
- \<h1\> to change font size.

12. The \<li\> and \<option\> tags always start with a new line.

13. We do not use the "title" attribute for the \<a\> tag.

Incorrect:
```html
<a href="/something" title="Something">Click here</a>
```

Correct:
```html
<a href="/something">Something</a>
```

14. We do not use the "title" attribute for the \<img\> tag. Just an "alt" attribute.
The "alt" attribute must always be declared, but we do not have to specify its value unless we know it
what to type.

Incorrect:
```html
<img src="/something.jpg" alt="Lorem ipsum" title="Lorem ipsum">
```
Correct:
```html
<img src="/something.jpg" alt="Lorem ipsum">
<img src="/something-2.jpg" alt="">
```

15. We do not group the \<a\> tag.

Incorrect:
```html
<a href="/something">
    <h3>Lorem header</h3>
</a>
<a href="/something"">
    <img src="/something.jpg" alt="Lorem image">
</a>
```

Correct:
```html
<a href="/something">
    <h3>Lorem header</h3>
    <img src="/something.jpg" alt="Lorem image">
</a>
```

16. 
Links to external addresses must have the "target" attribute with the value "_blank" - they must open in a new tab.

17. We save the phone numbers in the \<a\> tag as below to enable them to click on touch devices:

```html
<a href=”Tel:123456789”>123-456-789</a> 
```
18. The \<iframe\> tag has no content.

Incorrect:
```html
<iframe src="/something.html">Lorem subpage</iframe>
```

Correct:
```html
<iframe src="/something.html"></iframe>
```

19. In the form, \<input\> must have "type" and "name" attributes.


20. In the form for the password field, use the attribute "type" with the value "password". For the email address we use the value "email".

21. In the form, the \<button\> tag used to send the form does not have to have a "role" attribute with a "submit" value. This is its default value and we do not add it. The attribute "roles" supplements if we want to change its purpose.

22. In the tables, we separate the header with the \<thead\> tag and the cells inside it as \<th\>. Table content put inside the \<tbody\> tag.

Example:  
Incorrect:
```html
<table>
    <tr>
        <td>No.</td>
        <td>Person</td>
    </tr>
     <tr>
        <td>1</td>
        <td>Jan Kovalsky</td>
    </tr>
     <tr>
        <td>2</td>
        <td>John Smith</td>
    </tr>
</table>
```

Correct:
```html
<table>
    <thead>
        <tr>
            <th>No.</th>
            <th>Person</th>
        </tr>
    </thead>
    <tbody>
         <tr>
            <td>1</td>
            <td>Jan Kovalsky</td>
        </tr>
         <tr>
            <td>2</td>
            <td>John Smith</td>
        </tr>
    </tbody>
</table>
```

##Supplement
The following articles complement this information.
Keep in mind that articles have less priority in case of two conflicting information. This is because some of the rules are tailored to our needs. 
- https://github.com/hail2u/html-best-practices  
- https://www.themelocation.com/best-html5-practices/