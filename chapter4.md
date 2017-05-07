# Chapter 4
## Rails-flavored Ruby

### 4.1 Motivation
### 4.2 Strings and methods
`ApplicationHelper`: modules give us a way to package together related methods, which can then be mixed in to Ruby classes using include. When writing ordinary Ruby, you often write modules and include them explicitly yourself, **but in the case of a helper module Rails handles the inclusion for us. The result is that the full_title method is automagically available in all our views.**

###4.3 Other data structures
