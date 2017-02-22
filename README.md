# [hy-numpy](http://cs231n.github.io/python-numpy-tutorial/)

```clojure
=> (import [numpy :as np])
=> (setv a (np.array [1 2 3]))
=> (type a)
<type 'numpy.ndarray'>
=> a.shape
(3,)
=> (print a[0] a[1] a[2])
[1 2 3] [0L] [1 2 3] [1L] [1 2 3] [2L]
=> a[0]
array([1, 2, 3])
[0L]
=> a[-1]
array([1, 2, 3])
[-1L]
=>
```
