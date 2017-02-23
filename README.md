# [hy-numpy](http://cs231n.github.io/python-numpy-tutorial/)

* 1. numpy
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
* 2. numpy + matplotlib + pandas

```clojure
=> (import [matplotlib.pyplot :as plt])
=> (import [numpy :as np])
=> (import [pandas :as pd])
=> (setv df (pd.read_csv "https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data" :header None))
=> (setv x (. df.iloc [(slice 0 100)] [[0 2]] values))
=> (. x [(slice None 50)] [0])
array([ 5.1,  1.4])
=>
```
* 3. 用matplotlib绘图
```clojure
=> (import [matplotlib.pyplot :as plt])
=> (plt.plot [1 2 4 8])
[<matplotlib.lines.Line2D object at 0x10accb090>]
=> (plt.xlabel "x")
<matplotlib.text.Text object at 0x10a261dd0>
=> (plt.ylabel "y")
<matplotlib.text.Text object at 0x10a28ac90>
=> (plt.savefig "hy-test.png")
=>
```
```clojure
=> (import [matplotlib [pyplot :as plt]])
=> (import time)
=> (.xkcd plt)
<matplotlib.rc_context object at 0x10667ba10>
=> (def (, fig, ax) (.subplots plt))
(<matplotlib.figure.Figure object at 0x1057b1b50>, <matplotlib.axes._subplots.AxesSubplot object at 0x1067be8d0>)
=> (defn draw-circle [r0 r-max r-step]
...   (setv r r0)
...   (if (< r r-max) (do (-> (.Circle plt (, 0.5 0.5) r :color "black" :fill False) (ax.add-artist))
...       (setv r (+ r r-step))
...       (draw-circle r r-max r-step))))
=> (draw-circle 0.2 1 0.02)
=> (.text plt 0.5 0.5 (.upper "happy hack with hy!") :va "center" :ha "center")
<matplotlib.text.Text object at 0x104b54190>
=> (.show plt)

```
=> 
![](/draw_circle.png)
