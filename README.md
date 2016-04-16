# EvaluateService

Jef Raskin wrote in his book, **The Humane Interface: New Directions for Designing Interactive Systems**  Addision-Wesley, 2000 (page 142)

> "A better solution is a Calculate button or omnipresent menu command that allows you to take an arithmetic  expression such as 248.93 / 375, select it, and do the calculation whether you are in the word processor, communications package, drawing or presentation application, or just at the desktop level. In other words, it is an example of a universal function that can be used anywhere.

> Using an experienced computer and calculator operator as my test subject, with his word processor program open before him, I measured the total time it took for him to pick up the calculator, turn it on, do a simple addition, and return his hands to the keyboard to resume typing. It took him 7 seconds. I then measured the time it took him to use the built-in calculator. He had to move the cursor to the menu bar at the top of the screen, find the calculator program, open the calculator, enter the sum, then click back to the word processor so he could resume typing. This took about 16 seconds."

Jeff Atwood wrote a [blog post](http://blog.codinghorror.com/my-giant-calculator/) about this problem.

EvaluateService does exactly what they are asking for: it adds a pervasive Calculate command-key to the Macintosh.

by David Phillip Oster.

## To Install, 

0.) You can use the compiled, signed copy by opening Evaluate.dmg, 
or 
you can compile the source using Xcode to open the EvaluateService.xcodeproj. If you compile from source, change the bundle ID , since I own the com.turbozen prefix.

1.) place it in you Library/Services directory (Hold to the Option key on the Finder's 'Go' menu to find your Library folder.

2.) In System Preferences > Keyboard >  Shortcuts > Services  in the Text section check the checkbox to enable "Evaluate Expressions" click on the right edge of its table row to add a command-key-equivalent. I like to use <Command><Shift>-8(⌘⇧8), which used to be 'Evaluate applescript' before Apple broke 'Evaluate applescript'.

## To Use:
 
in just about any program where you can enter text, you can now enter an arithmetic expression like 22.80  + 45.7, select it, and type ⌘⇧8, and the selection is replaced by the evaluation. If you happen to select a few more characters before or after, they are preserved, and you always have undo  (⌘Z), to undo the effect.  It's using ordinary C double-precision floating point math, and understand basic plus, minus, times, divide, with precedence and parentheses. In addition to ordinary ints and floats, it also understand C-style 0xFFF for hexadecimal notation of integers. Under the hood, it's using a vanilla recursive-descent expression parser. 

## Summary

**EvaluateService** is a little service in the services menu.  

• "Evaluate Expression" service, which returns the evaluation of a numeric expression as a string.

The service information is stored in Info.plist and read by the system during login. Take a look at the "Application Settings" to see how the service information is specified. Details on the various entries can be found in the  documentation, in "Services" under "Programming Topics."

To install EvaluateService, copy it into ~/Library/Services .

## License
• Apache license version 2


