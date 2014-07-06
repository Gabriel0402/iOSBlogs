How do I declare a block in Swift
=======

###Swift blocks (closures) syntax

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
blockName: (parameters) -> returnType =  {(parameters) -> returnType in
                                            statements
                                         }
```

###As a property:

```objective-c
@property (nonatomic, copy) returnType (^blockName)(parameterTypes);
```

```objective-c

```
