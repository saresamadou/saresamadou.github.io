+++
author = "Samadou"
title = "Spring mvc exception handling"
date = "2022-09-10"
description = "Exception handling in spring rest"
tags = [
    "Exception handling",
]
+++

# Exception handler

## A try…catch block can help catch exceptions and return an appropriate response.

```java
try {
// do something
} catch (Exception ex) {
// handle exception
}

```

## Define a custom controller, A custom error controller can be used to handle the error in a Spring 5 application.

```java
@RestController
public class CustomErrorController implements ErrorController {
@RequestMapping(“/error”)
public String handle() {
return “Oops, can’t process that!”;
}
}

```

## Template Pages

- Error code-based HTML pages
- Replaces the default Whitelabel page
- Can use template engines; e.g., Thymeleaf
- Pages can be static or dynamic

## The Whitelabel page

## Apply @ResponseStatus Annotation

## Creating ControllerAdvice

- Handle the exceptions at a global, or application level
- Control which exceptions are handled by advice
- Control to which controllers the advice applies to

## Use @ExceptionHandler Annotation

- Controller-level exception 
- Annotated methods
- Customize response headers
- Custom response body

* Multiple : A controller can contain multiple exception handlers
* Target exceptions : Each handler can accept multiple exceptions that it handles
* No try…catch Exception handlers exist outside the methods

```java
//An exception handler
@ExceptionHandler
public String method(Params... params, Exception ex) {
// handle the exception
}
// Accept parameters to help with the exception handling and provide response
```
## Using @ControllerAdvice
