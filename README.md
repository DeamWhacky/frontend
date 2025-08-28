html notes: 
idk pretty intuitive

css notes:
1> Inheritance -

^some properties are inherited by child elements from parent elements
for eg: font properties put inside html or body rulesets will be inherited by all elements in the web page (can be stopped by color: initial)
some exceptions like form elements, input, label, button, select do not inherit any rulesets (can be forced by "font-family: inherit")
some exceptions like margin and border properties are not inherited by any elements (can be forced by "margin: inherit")

note: rulesets can be overriden if child element is specifically targetted, like if html and body both have a color set, the body ruleset will be valid, because body, being a child of html is explicitly ruled.

2> Specificity -

^if multiple rulesets are created for the same element-> then specificity is checked
inline css has the most power, followed by id selector, followed by class and then element, and finally * selector which has zero specificity
if multiple rulesets apply to the same element, then specificity is calculated, whichever one has more "weight" is considered a valid ruleset
if specificity is calculated to be the same, then whichever ruleset is read last is considered valid (cascading)
if !important is present, it will override everything even if it has low specificity 

so if multiple rulesets apply to the same element:
 first, importance is checked -> then specificity (if all important or none) -> then cascading (if equal specificity and importance)
