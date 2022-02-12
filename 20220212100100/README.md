# Vim variable scopes

VimScript has the following variable scopes, denoted by a corresponding
prifix letter:

|Scope       |Prefix           |Purpose                                        |
|:----------:|:---------------:|----------------------------------------------:|
|global      |`g:` or no prefix|                                               |
|buffer-local|`b:`             |                Separate values between buffers|
|window-local|`w:`             |       Separate values between winodows(splits)|
|tab-local   |`t:`             |           Separate values between tabs (views)|
|script-local|`s:`             |Variable accessible only within the script file|
|built-in    |`v:`             |                       Variables built into Vim|

---

References:

* Vimscript Variable Scopes | Learn Vim (p5 of 6) 
  <https://learnvim.irian.to/vimscript/vimscript_variable_scopes/>

---

    #literature-note #plugins
