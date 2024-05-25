---
sidebar_position: 4
title: April
description:  Understanding how arrays work & their overall time complexity
---

## Question

Given a string `s` containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.
3. Every close bracket has a corresponding open bracket of the same type.

**Example 1:**

```
Input: s = "()"
Output: true

```

**Example 2:**

```
Input: s = "()[]{}"
Output: true

```

**Example 3:**

```
Input: s = "(]"
Output: false

```

## Code
```kotlin
import junit.framework.TestCase.assertEquals

/**
 * Without changing anything in the main function
 * Ensure all the test cases pass
 */

fun main() {

    val values = listOf(
    "()" to true,
    "()[]{}" to true,
    "(]" to false,
    "([)]" to false,
    "{[]}" to true,
    "{" to false,
    "({[()]})" to true,
    "[({})](]" to false,
    "{[({})]}" to true,
    "{[(])}" to false,
    "(){}[]" to true,
    "[{]}" to false,
    "(({{[[]]}}))" to true,
    "[(])" to false,
    "{}()[({})]" to true,
    "({}[(]})" to false,
    "{[([{})]({})]}" to false,
    "(([]){})" to true,
    "[(]){}" to false,
    "([]){}[({})]" to true,
    "[{}]" to true,
    "{([])}" to true,
    "(()[]{})" to true,
    "([{}]))" to false,
    "({}[(){}])" to true
    )


    /**
     * Ground Rules : 
     * the isValid function should use a List
     **/
    values.forEach{ (value, answer) ->
        assertEquals(value.isValid(), answer)
    }

    /**
     * Ground Rules : 
     * the valid function should not use a List
     **/
    values.forEach{ (value, answer) ->
        assertEquals(value.valid(), answer)
    }
    println("Everything Passed!!!")
}
```