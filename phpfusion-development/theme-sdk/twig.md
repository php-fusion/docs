---
description: Twig is a modern template engine for PHP
---

# Twig

#### Expressions

Expressions can be used in **{% blocks %}** and **${ expressions }**.

```text
Operator    Description
==          Does the left expression equal the right expression?
+           Convert both arguments into a number and add them.
-           Convert both arguments into a number and substract them.
*           Convert both arguments into a number and multiply them.
/           Convert both arguments into a number and divide them.
%           Convert both arguments into a number and calculate the rest of the integer division.
~           Convert both arguments into a string and concatenate them.
or          True if the left or the right expression is true.
and         True if the left and the right expression is true.
not         Negate the expression.
```

#### Conditional expressions

If I recall correctly Twig doesn't support `||` and `&&` operators, but requires `or` and `and` to be used respectively. I'd also use parentheses to denote the two statements more clearly although this isn't technically a requirement.

```text
{%if ( fields | length > 0 ) or ( trans_fields | length > 0 ) %}
```

**Expressions**

For more complex operations, it may be best to wrap individual expressions in parentheses to avoid confusion:

```text
{% if (foo and bar) or (fizz and (foo + bar == 3)) %}
```



