# General Principals:

## Steps to developing a usable algorithm.
- Model the problem.
- Find an algorithm to solve it.
- Fast enough? Fits in memory?
- If not, figure out why.
- Find a way to address the problem.
- Iterate until satisfied.

---

## 1. UNION-FIND:
- 1.1 Quick-find:
    + dynamic connectivity
        * Create: `N`
        * Union: `N`
        * Find: `1`
    + Expensive in union operation. 
- 1.2 Quick-Union (QU)
    + Tree Structure
        * Create: `N`
        * Union: `N`
        * Find: `N`
    + Good for union operation than 1.1 but not the best 
- 1.3 Weighted QU
    + Create: `N`
    + Union: `N`
    + Find: `log-(base 2)-N`
- 1.4 QU + Path Compression
    + Much more Improved over 1.3
- 1.5 Weighted QU + Path Compression


## 2. Pecolation


---

# Big Theta
When we use big-Θ notation, we're saying that we have an asymptotically tight bound on the running time. "Asymptotically" because it matters for only large values of n nn. "Tight bound" because we've nailed the running time to within a constant factor above and below.

# Big O
We say that the running time is "big-O of f(n) f(n)f, left parenthesis, n, right parenthesis" or just "O of f(n) f(n)f, left parenthesis, n, right parenthesis." We use big-O notation for asymptotic upper bounds, since it bounds the growth of the running time from above for large enough input sizes.

we can say that because the worst-case running time of binary search is \Theta(\log_2 n) Θ(log 2 n), it's also O(\log_2 n) O(log 2 n)O, left parenthesis, log, start subscript, 2, end subscript, n, right parenthesis. The converse is not necessarily true: as we've seen, we can say that binary search always runs in O(\log_2 n) O(log 2 n)O, left parenthesis, log, start subscript, 2, end subscript, n, right parenthesis time but not that it always runs in \Theta(\log_2 n) Θ(log 2 n) time. Because big-O notation gives only an asymptotic upper bound, and not an asymptotically tight bound, we can make statements that at first glance seem incorrect, but are technically correct. For example, it is absolutely correct to say that binary search runs in O(n) O(n)O, left parenthesis, n, right parenthesis time. That's because the running time grows no faster than a constant times n nn. In fact, it grows slower.

# Big-Ω (Big-Omega) notation
Sometimes, we want to say that an algorithm takes at least a certain amount of time, without providing an upper bound. We use big-Ω notation; that's the Greek letter "omega."

---

Python implementation:
## Bubble Sort:
```
sl = [2,3,4,1,2,55,22,3,4,1,1,77,99,23,44,223,6,7, -98, -7658, 98, 87]
itr = 0
flag = True
while(itr <= len(sl) and flag):
  flag = False
  for cntr, index in enumerate(sl[itr:]):
    try:
        n = len(sl) - cntr
        n_1 = len(sl) - 1 - cntr
        if (sl[n] < sl[n_1]):# and (n > -1) and (n_1 > -1):
            tmp = sl[n]
            sl[n] = sl[n_1]
            sl[n_1] = tmp
            flag = True
    
    except Exception as e:
        pass
  itr += 1
```