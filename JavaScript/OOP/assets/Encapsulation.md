
means keeping properties and methods private inside of the class inaccessible outside the class rest are exposed as a public interface which we call API

Reasons
1. prevent code outside of the class to change data inside of the class
2. since data is private and only available for private use we can change inside code knowing that outside code will be unaffected.

![[Encapsution_1.png]]

developers use a convention to put underscore before the property name to indicate it is supposed to be a private property. ***`this._movements`*** but this does not make field private.

following the convention we can provide public interface for movements but restrict mutations. line 24.

class fields proposal 

public fields and private fields
public method and private method
look into static version of above four

movements and locale has to be added to each instance look into 

fields have to be declared outside of any method in class body directly

get accessor's name can't be  private fields name unlike 

hash names can't be accessed outside of the class MDN

they behave like normal vars inside class can be re-assigned like let and can be accessed via scope chain but only inside the class outside the class .#name give error.

private methods are not added to prototype they are kept  in js's internal property ***`[[PrivateMethods]]`*** private methods are meant to only be accessed in the class and not outside

