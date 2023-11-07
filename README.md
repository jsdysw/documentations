# numpy_documentation

### 
| functions | usage |
| --- | --- |
| np.array() | ````np.where(```` |
| np.arange(3) | ````array([0,1,2])```` |


### All & Any
| usage | output example |
| --- | --- |
| np.any(a>5) | ````True```` |
| np.all(a<10) | ````True"```` |


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


