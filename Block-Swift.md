How do I declare a block (closure) in Swift
=======

###Swift block (closure) syntax
```objective-c
{ (parameters) -> returnType in
  statements
}
```
__Note__: __in__ is a keyword

###As a local variable:

__Objective-C__
```objective-c
returnType (^blockName)(parameters) = ^returnType(parameters) {...};
```
__Swift__
```objective-c
let blockName = { (parameters) -> returnType in
                    statements
                }
```

###As a property:
__Objective-C__
```objective-c
@property (nonatomic, copy) returnType (^blockName)(parameterTypes);
```
__Swift__
```objective-c
let blockName: (parameters) -> returnType
```

###As a method parameter:

__Objective-C__
```objective-c
- (void)someMethodThatTakesABlock:(returnType (^)(parameterTypes))blockName;
```
__Swift__
```objective-c
func someMethodThatTakesABlock(blockName: (parameters) -> returnType) {
    Statements
}
```

###As an argument to a method call:

__Objective-C__
```objective-c
[someObject someMethodThatTakesABlock: ^returnType (parameters) {...}];
```
__Swift__
```objective-c
someMethodThatTakesABlock({ (parameters) -> returnType in
    Statements
})
```

###As a typedef (typealias):
__Objective-C__
```Objective-C
typedef returnType (^TypeName)(parameterTypes);
TypeName blockName = ^returnType(parameters) {...};
```
__Swift__
```Objective-C
typealias TypeName = (parameters) -> returnType
let blockName: TypeName = { (parameter) -> returnType in
                             statements
                          }
```

----------

###Contact

Follow me on Twitter: [@kietnv](https://twitter.com/kietnv)

###References
* [fuckingblocksyntax.com](http://fuckingblocksyntax.com/)
* [hayageek.com](http://hayageek.com/swift-blocks-tutorial/)
* [learnswift.io](http://www.learnswift.io/blog/2014/6/9/writing-completion-blocks-with-closures-in-swift)
