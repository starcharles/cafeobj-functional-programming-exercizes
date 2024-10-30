# 2. Explain in which way fact(5) is computed

- steps

1. fact(5)

```cafeobj

fact(5) = 5 * fact(p 5)
        = 5 * fact(4)
        = 5 * 4 * fact(p 4)
        = 5 * 4 * fact(3)
        = 5 * 4 * 3 * fact(p 3)
        = 5 * 4 * 3 * fact(2)
        = 5 * 4 * 3 * 2 * fact(p 2)
        = 5 * 4 * 3 * 2 * fact(1)
        = 5 * 4 * 3 * 2 * 1 * fact(p 1)
        = 5 * 4 * 3 * 2 * 1 * fact(0)
        = 5 * 4 * 3 * 2 * 1 * 1
        = 120
```
