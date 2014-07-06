How do I declare a block (closure) in Swift
=======

###Swift bloc (closure) syntax
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
