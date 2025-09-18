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
 a id selector will always have more specificity than a class selector
    for eg :
        body article .checkclass {
            --
        }
        article #checkid {
            --
        }

    here the second ruleset will be valid because id is more specific, so we dont need to bother with calculating specificity

    but for eg:
        body article .checkclass {
            --
        }
        article .checkclass {
            --
        } 

    here we do need to calculate specificity because both have elements and class selectors, using calculation we find the first to be more specific


 2> absolute and relative units

 ^px
 basic, used for borders and other absolute details, not for setting font size (browser should handle that)

 ^%
 takes value relative to the parent for that property

 ^rem
 takes value relative to the root that is the html element

 ^em
 similar to % when used for properties in compounding children
 another use is to pair it properties like padding with font size
 eg:
    span {
        font-size: 3rem; //here font-size for span takes 3 times the root size
        padding: 0.5em;  //here padding is relative to its own font-size, so 0.5em means 1.5 times the root size
    }
 ^vw
 viewport width, used to increase/decrease element width, % also works, sometimes better

 ^vh
 viewport height, used to increase/decrease element height
 
note: rem is a fixed unit, 0.5 rem used in 2 different rulesets mean the same size because its dependent on the root and theres always only 1 root
this is not true for %, 50 percent used in 2 rulesets does not guarantee the same size because its dependent on its parent