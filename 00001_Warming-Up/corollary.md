Now we have combined operations, things are a bit more complicated, since you have to be **more careful with the order**.
For example, look at the program you have just written:

```puppet
program {
  Poner(Rojo)
  Mover(Este)
  Poner(Negro)
}
```

Operationally:

1. it drops one red stone
1. then, it moves to the east
1. then, it drops one black stone

Meaning: it drops one red stone in the initial position, and one black stone to the east

Now, look at this other program:

```puppet
program {
  Mover(Este)
  Poner(Rojo)
  Poner(Negro)
}
```

Operationally:

1. it moves to the east
1. then, it drops one red stone
1. then, it drops one black stone

Meaning: it drops one red and one black stone to the east of the initial position.

Moral: they don't do the same thing! Changing the order, changed the _what_.
