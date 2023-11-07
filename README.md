# numpy_documentation

### Basic
| functions | usage |
| --- | --- |
| np.array([1,2,3], dtype=np.float64) | ````array([1.,2.,3.])```` |
| np.array([[1,2,3], [1,2,3]], dtype=np.float64) | ````array([1.,2.,3.])```` |
| narray.dtype | ````dtype('float64')```` |
| narray.shape | ````(4,) or (4,3) or (4,3,4)```` |
| narray.reshape(3,) | ````(3,)```` |
| narray.reshape(3,-1) | ````(3,-1)```` |
| narray.reshape(1, 3,-1) | ````(1, 3,-1)```` |
| narray.flatten() | ````array([1, 3,-1])```` |

### indexing & slicing
| functions | usage |
| --- | --- |
| a[0][5] | ````(0,5) element```` |
| a[0,5] | ````(0,5) element```` |
| a[:,:] | ````all row, all col```` |
| a[1:3,:] | ````from row 1 to row2, all col```` |

### creation
| functions | usage |
| --- | --- |
| np.arange(3) | ````array([0,1,2])```` |
| np.zeros(shape=(2,2), dtype=np.int8) | ````array([0,0], [0,0])```` |
| np.ones(shape=(2,2)) | ````array([1,1], [1,1])```` |
| np.empty(shape=(2,2)) | ````array([?,?], [?,?])```` |
| np.identity(n=2, dtype=np.float32) | ````array([1.,0.], [0.,1.])```` |
| np.eye(N=2, M=2, k=1, dtype=np.float32) | ````array([0.,1.], [0.,0.])```` |
| np.diag(matrix, k=1) | ````return diagonal values starting from k index```` |

### random sampling
| functions | usage |
| --- | --- |
| np.random.uniform(0, 1, 10) | ````mean 0, std 1, 10 samples```` |
| np.random.normal(0, 1, 10) | ````mean 0, std 1, 10 samples```` |

### operation
| functions | usage |
| --- | --- |
| arr.sum() | ````sum of all elems```` |
| arr.sum(axis=1) | ````sum axis 1```` |
| arr.mean() | ````mean of all elems```` |
| arr.mean(axis=1) | ````mean axis 1```` |
| arr.std(axis=1) | ````std axis 1```` |
| arr.sqrt() | ````square root```` |
| np.vstack(a1, a2) | ````concat vertically```` |
| np.hstack(a1, a2) | ````concat horizontally```` |
| np.concatenate((a1, a2), axis=0) | ````concat through axis=0```` |

### array operation
| functions | usage |
| --- | --- |
| a + b | ````elementwise sum```` |
| a * b | ````elementwise multiply```` |
| a - b | ````elementwise subtraction```` |
| a.dot(b) | ````a dot product b```` |
| a.T | ````a transpose```` |
| a +, -, * scalar | ````broadcasting```` |

### All & Any
| usage | output example |
| --- | --- |
| np.any(a>5) | ````True```` |
| np.all(a<10) | ````True```` |


### comparison operation
| usage | output example |
| --- | --- |
| a > b | ````array([False, True, False], dtype=bool)```` |
| a == b | ````array([False, True, False], dtype=bool)```` |
| np.logical_and(a>0, a<3) | ````array([False, True, False], dtype=bool)```` |
| np.logical_not(b) | ````array([False, True, False], dtype=bool)"```` |
| np.logical_or(b) | ````array([False, True, False], dtype=bool)"```` |


### Where
| usage | output example |
| --- | --- |
| np.where(a>5, 3, 2) | ````array([3,3,2])```` #where(condition, True, False) |
| np.where(a>5) | ````(array([6,7,8]))```` #return index |
| np.isnan(a) | ````array([False,True,False])````|
| np.isfinite(a) | ````array([False,True,False])````|

### argmax & argmin
| usage | output example |
| --- | --- |
| np.argmin(a) | ````1```` |
| np.argmax(a) | ````5```` |
| np.argmin(a, axis=1) | ````array([6,7,8])```` |
| np.argsort() | ````array([3,1,2])```` # sorted index|

### boolean index & fancy index
| usage | output example |
| --- | --- |
| a[a>3] | ````array([4, 8, 9, 7])```` # return value greater than 3 |
| a[np.array([1,1,2])] | ````array([4, 4, 9])```` # return values of given indices |
| a[np.array([0,0]), np.array([1,0])] | ````array([4, 9])```` # return (0,0) and (0,1) |

### numpy io
| usage | output example |
| --- | --- |
| np.loadtxt("./n.txt") | ````load n.txt```` |
| np.savetxt('n.csv, test_array, fmt="%.2e", delimiter=",") | ````save txt```` |
| a.astype(int) | ````convert type```` |
| np.save("npy_test.npy", arr=test_array) | ````save as .npy```` |
| np.load("npy_test.npy") | ````load .npy```` |


