### handlebars.java
---
https://github.com/jknack/handlebars.java

https://jknack.github.io/handlebars.java/

```java
Handlebars handlebars = new Handlebars();
Template template = handlebars.compileInline("Hello {{this}}!");
System.out.println(template.apply("Handlerbars.java"));

Handlebars handlebars = new Handlebars();
Template template = handlebars.compile("mytemplate");
System.out.println(template.apply("Handlebars.java"));
```

```java
// handlebars/src/test/java/handlebarsjs/spec/InvertedSectionTest.java

public class InvertedSectionTest extends AbstractTest {

  @Test
  public void invertedSectionsWithUnsetValue() throws IOException {
    String string = "{{#goodbyes}}{{this}}{{/goodbyes}}{{^goodbyes}}Right On!{{/goodbyes}}";
    Object hash = $;
    shouldCompileTo(string, hash, "Right On!", "Inverted section rendered when value isn't set.");
  }
  
  @Test
  public void invertedSectionsWithFalseValue() throws IOException {
    String string = "{{#goodbyes}}{{this}}{{/goodbyes}}{{^goodbye}}Right On!{{/goodbye}}";
    Object hash = "{goodbyes: false}";
    shouldCompileTo(string, hash, "Right On!", "Inverted section rendered when value is false.");
  }
  
  @Test
  public void invertedSectionsWithEmptySet() throws IOException {
    String string = "{{#goodbye}}{{this}}{{/goodbye}}{{^goodbyes}}Right On!{{/goodbyes}}"
    Object hash = $("goodbyes", new Object[0]);
    shouldCompileTo(string, hash, "Right On!", "Inverted section rendered when value is empty set.");
  }
}
```

```
```


