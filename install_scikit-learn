For Mac OSX: 
1. install [pip](https://pip.readthedocs.io/en/stable/installing/#upgrading-pip);  
2. install numpy,scipy use pip;
3. run sudo pip install scikit-learn;

However, when I did above steps, I got some Errors like:

Traceback (most recent call last):
File "<stdin>", line 1, in <module>
File "/Library/Python/2.7/site-packages/sklearn/__init__.py", line 57, in <module>
from .base import clone
File "/Library/Python/2.7/site-packages/sklearn/base.py", line 11, in <module>
from .utils.fixes import signature
File "/Library/Python/2.7/site-packages/sklearn/utils/__init__.py", line 10, in <module>
from .murmurhash import murmurhash3_32
File "numpy.pxd", line 155, in init sklearn.utils.murmurhash (sklearn/utils/murmurhash.c:5029)
ValueError: numpy.dtype has the wrong size, try recompiling

[解决](http://kubicode.me/2016/04/22/Python/Solve-numpy-dtype-In-ValueError-when-using-scikit-learn/)

以为是numpy包的问题:卸载重装之后还是照样有问题-_-
网上给的建议大都是直接卸载再全部重装，将numpy、scipy和scikit-learn全部卸载了，然后
pip install -U numpy scipy scikit-learn
装起来。结果一样有问题-_-
继续查资料时终于发现有用的方法了:
[scikit-learn_recompiling](http://scikit-learn-general.narkive.com/kMA6mRCk/valueerror-numpy-dtype-has-the-wrong-size-try-recompiling)  
就是不用使用pip install scikit-learn安装，卸载之后直接使用[git上scikit-learn](https://github.com/scikit-learn/scikit-learn)的自己安装
``` shell
git clone https://github.com/scikit-learn/scikit-learn
make
sudo python setup.py install
```
ps：这个时候直接安装可能会出
```
RuntimeError: Running cythonize failed!
```
Error提示,这时候安装一下cpython即可
```
pip install cython
```
如果提示
```
nosetests -v -t scikit-learn
Nosetests no such file.
```
安装nose：
```
sudo pip install nose
```
nosetests 出现[#1708](https://github.com/scikit-learn/scikit-learn/issues/1708),目前未解决，但是scikit-learn已经安装成功。


