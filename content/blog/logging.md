+++
author = "SARE Samadou"
title = "Logging"
date = "2021-04-17"
description = "About Logging in java."
tags = [
"Java",
"Logging"
]
categories = [
"themes",
"syntax",
]
series = ["Themes Guide"]
aliases = ["migrate-from-jekyl"]
+++

## Schema

   - APP (triggering logger) -> LOGGER(Filter) ->(send LogRecord) HANDLER (Filter, Formatter) -> Appender (External system, LogManager)
  
  
## What is the story ?
  Application trigger logging .....
  
 
## Details
  
  - Default Handler is ConsoleHandler with INFO level
  - Log Formatters: change the structure of the log message
    - SimpleFormatter: HumanReadable way of depicting the log message.
    - XMLFormatter: Write the log message to standard XML format.

 - Logging Filter
 - LogManager: 
    - Create and manage the logger, is a singleton. 
    - You can use custom logging.properties to manage logger, handlers, level
    - LogManager.getLogManager().readConfiguration(PATH_TO_LOGGING.PROPERTIES) 
 

## Logging best pratices

- Be precise: Who , what, when, where and the result
- No sensitive Data Be carefull with sensitive Data
- Right log level: 
- Best log is readeable by machine and human 
- Don't log too much
- Don't log too little

### Log method
LOGGER.log(Level.INFO, "")

LOGGER.logp(Level.INFO, LogExample.class.getName(), "sourceMethodName", "");

LOGGER.logrb(Level.INFO, ResourceBundle.getBundle("eu_EU"), "");
