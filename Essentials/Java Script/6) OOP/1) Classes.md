We know that we can create objects using factory or constructor functions. We can use classes.
```js
class Teacher{
    constructor(name){
        this.fname=name;
    }
  
    teach(){
        console.log("Teaching");
    }
};
  
const teacher=new Teacher("Giga nigga");
console.log(teacher);
console.log(teacher.fname);
teacher.teach();
```
The `constructor()` is a built in method for classes. `teach()` here on the other hand is our made method.

##### Static members
```js
class Player{
    constructor(name,age){
        this.name=name;
        this.age=age;
        this.activePlayer=0;
    }
  
    playGame(){
        console.log("Playing a game.");
        this.activePlayer++;
    }
};
  
const player1=new Player("Giga nigga","911");
player1.playGame();
player1.playGame();
player1.playGame();
console.log(player1);
```
Whenever playgame function gets called, active player increases.
Since activeplayer is defined for one object only, if you use another player object playgame method, it will still be 3.

So you can use static element method instead.
```js
class Player{
    static activePlayer=0;
    constructor(name,age){
        this.name=name;
        this.age=age;
    }
  
    playGame(){
        console.log("Playing a game.");
        Player.activePlayer++;
    }
};
  
const player1=new Player("Giga nigga","911");
const player2=new Player("Giga nigga2","911");
player1.playGame();
player1.playGame();
player1.playGame();
player2.playGame();
player2.playGame();
player2.playGame();
console.log(Player.activePlayer); //6
```
Now it's defined for all the class and not object only.
You can define an static method as well.
```js
static jump(){
	console.log("Jump");
}
```

##### getter and setter
```js
class BankAccount{
    constructor(ownerName,curr_balance){
        this.name=ownerName;
        this.curr_balance=curr_balance;
    }
  
    get balance(){
        return this.curr_balance;
    }
  
    set balance(val){
        if(typeof val==="number"){
            this.curr_balance=val;
        }
    }
  
    deposit(){
        console.log("Deposit to account");
    }
  
    withdraw(){
        console.log("Withdraw from account");
    }
};
  
const acc=new BankAccount("Giga nigga",3000);
acc.balance=5000;
console.log(acc);
```

##### Inheritance
When you want another class to inherit some attributes and methods from another class, we can use these methods below:
```js
class Person{
    constructor(name,age){
        this.fname=name;
        this.age=age;
    }
  
    talk(){
        console.log("hello");
    }
}
  
class Actor extends Person{
    act(){
        console.log("Act...")
    }
}
  
const actor=new Actor("Ali",21);
actor.act();
actor.talk();
```
*!Note:* And if you don't give it any attributes when you're declaring it, and you use the elements defined in the class, it will refer them as undefined.

Another important is that if you define a constructor in the child class, and then you declare a new object based on that, the elements for that objects are overridden. Meaning you need to consider new element defined in the child class's constructor.
```js
class Person{
    constructor(name,age){
        this.fname=name;
        this.age=age;
    }
  
    talk(){
        console.log("hello");
    }
}
  
class Actor extends Person{
	constructor(salary){
		this.salary=salary;
	}
    act(){
        console.log("Act...")
    }
}
  
const actor=new Actor("Ali",21);
console.log(actor);
```
The code above will cause an error. Because we can't define name and age for an actor object. We only can give it the salary attribute. To avoid the problem above, we can use `super()` method.
```js
class Actor extends Person{
	constructor(fname,age,salary){
		super(fname,age);
		this.salary=salary;
	}
    act(){
        console.log("Act...")
    }
}
```

**Method overriding**
```js
class Person{
    constructor(fname){
        this.fname=fname;
    }
  
    talk(){
        console.log(`My name is ${this.fname}`);
    }
}
  
const person1=new Person("Ali");
  
class Doctor extends Person{
    talk(){
        console.log("I'm a doctor");
    }
}
  
const doc1=new Doctor("Hossein");
  
doc1.talk(); //I'm a doctor
```
The talk method is overridden because we used same name for it's function. You can use `super()` here as well.
```js
talk(){
		super.talk();
        console.log(`My name is ${this.fname}`);
    }
    
    //My name is Hossein
    //I'm a doctor
```
As you can see, both talk methods are called.

##### Polymorphism