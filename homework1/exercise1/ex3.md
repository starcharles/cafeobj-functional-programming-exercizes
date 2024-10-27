# 3. Explain in which way oedc‐fact(5) is computed

- steps

1. oedc-fact(5)

- code

```cafeobj

open NAT .
    op cond : Bool Nat Nat -> Nat .
    op g : Nat Nat -> Nat .
    op oedc-fact : Nat -> Nat .
    vars X Y : Nat . var NzX : NzNat .
    -- cond
    eq cond(true, X, Y) = X .
    eq cond(false, X, Y) = Y .
    -- g
    eq g(X,Y) = cond(X > Y, g(X, 2 * Y, Y) * g(sd(X,Y), 2 * Y), X) .
    -- oedc-fact
    eq oedc-fact(0) = 1 .
    eq oedc-fact(NzX) = g(NzX, 1) .
    -- compute
    red oedc-fact(1000) .
close

```

- execution of oedc-fact(5)

```cafeobj

oedc-fact(5)
    = g(5, 1)
    = cond(5 > 1, g(5, 2 * 1) * g(sd(5, 1), 2 * 1), 5)
    = cond(true, g(5, 2 * 1) * g(sd(5, 1), 2 * 1), 5)
    = g(5, 2) * g(sd(5, 1), 2)
    // sdが何をやつかわからないのでパス




```
