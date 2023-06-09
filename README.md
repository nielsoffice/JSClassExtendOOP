# JSClassExtend
JavaScript class Extend using super() function that can use for constructor

```JS
class Character {
  constructor(name, weapon) {
    this.name = name;
    this.weapon = weapon;
  }
  attack() {
    return 'atack with ' + this.weapon
  }
}

class Elf extends Character { 
  constructor(name, weapon, type) {
    // console.log('what am i?', this); this gives an error
    super(name, weapon) // Using super() function to access parent constructor
    console.log('what am i?', this);
    this.type = type;
  }
}

class Ogre extends Character {
  constructor(name, weapon, color) {
    super(name, weapon);  // Using super() function to access parent constructor
    this.color = color;
  }
  makeFort() { // this is like extending our prototype.
    return 'strongest fort in the world made'
  }
}
```

```JS
const houseElf = new Elf('Dolby', 'cloth', 'house')
//houseElf.makeFort() // error
const shrek = new Ogre('Shrek', 'club', 'green')
shrek.makeFort()
```

MAKE PRIVATE PROPERTIES AND METHOD JS CLASS 

```JS
class Employee {
    #name = "Test"; // private field
    setName(name) {
        this.#name = name;
    }
}
```

```JS
const emp = new Employee();
emp.#name = 'New'; // error
emp.setName('New'); // ok
```

```JS
class Employee {
    #name = "Test";
    constructor(name) {
        this.#setName(name) // ok
    }
    #setName(name) { // Private method
        this.#name = name;
    }
}
```

```JS
const emp = new Employee('New'); // ok
emp.#setName('New'); // error
```
