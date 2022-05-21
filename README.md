# huashan
赵林是个垃圾
赵林没人要
总结了 11 种 Numpy 的高级操作
01数组上的迭代
NumPy 包含一个迭代器对象numpy.nditer。它是一个有效的多维迭代器对象，可以用于在数组上进行迭代。数组的每个元素可使用 Python 的标准Iterator接口来访问。
 
如果两个数组是可广播的，nditer组合对象能够同时迭代它们。假设数 组a具有维度 3X4，并且存在维度为 1X4 的另一个数组b，则使用以下类型的迭代器(数组b被广播到a的大小)。
 
02 数组形状修改函数
1.ndarray.reshape
函数在不改变数据的条件下修改形状，参数如下：
ndarray.reshape(arr, newshape, order)
 
2.ndarray.flat
函数返回数组上的一维迭代器，行为类似 Python 内建的迭代器。
 
3.ndarray.flatten
函数返回折叠为一维的数组副本，函数接受下列参数：
ndarray.flatten(order)
其中：
•	order：‘C’ — 按行，‘F’ — 按列，‘A’ — 原顺序，‘k’ —元素在内存中的出现顺序。
 
03 数组翻转操作函数
1.numpy.transpose
函数翻转给定数组的维度。如果可能的话它会返回一个视图。函数接受下列参数：
numpy.transpose(arr, axes)
其中：
•	arr：要转置的数组
•	axes：整数的列表，对应维度，通常所有维度都会翻转。
 
 
2. numpy.ndarray.T
该函数属于ndarray类，行为类似于numpy.transpose.
 
3.numpy.swapaxes
函数交换数组的两个轴。这个函数接受下列参数：
numpy.swapaxes(arr, axis1, axis2)
其中：
•	arr：要交换其轴的输入数组
•	axis1：对应第一个轴的整数
•	axis2：对应第二个轴的整数
 
4.numpy.rollaxis
numpy.rollaxis() 函数向后滚动特定的轴，直到一个特定位置。这个函数接受三个参数：
numpy.rollaxis(arr, axis, start)
其中：
•	arr：输入数组
•	axis：要向后滚动的轴，其它轴的相对位置不会改变
•	start：默认为零，表示完整的滚动。会滚动到特定位置。
 
04 数组修改维度函数
1.numpy.broadcast_to
函数将数组广播到新形状。它在原始数组上返回只 读视图。它通常不连续。如果新形状不符合 NumPy 的广播规则，该函数可能会抛出ValueError。该函数接受以下参数：
numpy.broadcast_to(array, shape, subok)
 
2.numpy.expand_dims
函数通过在指定位置插入新的轴来扩展数组形状。该函数需要两个参数：
numpy.expand_dims(arr, axis)
其中：
•	arr：输入数组
•	axis：新轴插入的位置
 
3.numpy.squeeze
函数从给定数组的形状中删除一维条目。此函数需要两 个参数。
numpy.squeeze(arr, axis)
其中：
•	arr：输入数组
•	axis：整数或整数元组，用于选择形状中单一维度条目的子集
 
05 数组的连接操作
NumPy中数组的连接函数主要有如下四个：
•	concatenate 沿着现存的轴连接数据序列
•	stack 沿着新轴连接数组序列
•	hstack 水平堆叠序列中的数组(列方向)
•	vstack 竖直堆叠序列中的数组(行方向)
1.numpy.stack
函数沿新轴连接数组序列，需要提供以下参数：
numpy.stack(arrays, axis)
其中：
•	arrays：相同形状的数组序列
•	axis：返回数组中的轴，输入数组沿着它来堆叠
 
2.numpy.hstack
是numpy.stack()函数的变体，通过堆叠来生成水平的单个数组。
 
3.numpy.vstack
是numpy.stack()函数的变体，通过堆叠来生成竖直的单个数组。
 
4.numpy.concatenate
函数用于沿指定轴连接相同形状的两个或多个数组。该函数接受以下参数。
numpy.concatenate((a1, a2, …), axis)
其中：
•	a1, a2, ...：相同类型的数组序列
•	axis：沿着它连接数组的轴，默认为 0
 
06 数组的分割操作
NumPy中数组的数组分割函数主要如下：
•	split 将一个数组分割为多个子数组
•	hsplit 将一个数组水平分割为多个子数组(按列)
•	vsplit 将一个数组竖直分割为多个子数组(按行)
1.numpy.split
该函数沿特定的轴将数组分割为子数组。函数接受三个参数：
numpy.split(ary, indices_or_sections, axis)
其中：
•	ary：被分割的输入数组
•	indices_or_sections：可以是整数，表明要从输入数组创建的，等大小的子数组的数量。如果此参数是一维数组，则其元素表明要创建新子数组的点。
•	axis：默认为 0
 
2.numpy.hsplit
split()函数的特例，其中轴为 1 表示水平分割。
 
3.numpy.vsplit
split()函数的特例，其中轴为 0 表示竖直分割，无论输入数组的维度是什么。
 
07 数组元素操作
NumPy中数组操作函数主要如下：
•	resize 返回指定形状的新数组
•	append 将值添加到数组末尾
•	insert 沿指定轴将值插入到指定下标之前
•	delete 返回删掉某个轴的子数组的新数组
•	unique 寻找数组内的唯一元素
1.numpy.resize
函数返回指定大小的新数组。如果新大小大于原始大小，则包含原始数组中的元素的重复副本。如果小于则去掉原始数组的部分数据。该函数接受以下参数：
numpy.resize(arr, shape)
其中：
•	arr：要修改大小的输入数组
•	shape：返回数组的新形状
 
2.numpy.append
函数在输入数组的末尾添加值。附加操作不是原地的，而是分配新的数组。此外，输入数组的维度必须匹配否则将生成ValueError。函数接受下列函数：
numpy.append(arr, values, axis)
其中：
•	arr：输入数组
•	values：要向arr添加的值，比如和arr形状相同(除了要添加的轴)
•	axis：沿着它完成操作的轴。如果没有提供，两个参数都会被展开。
 
3.numpy.insert
函数在给定索引之前，沿给定轴在输入数组中插入值。如果值的类型转换为要插入，则它与输入数组不同。插入没有原地的，函数会返回一个新数组。此外，如果未提供轴，则输入数组会被展开。
insert()函数接受以下参数：
numpy.insert(arr, obj, values, axis)
其中：
•	arr：输入数组
•	obj：在其之前插入值的索引
•	values：要插入的值
•	axis：沿着它插入的轴
 
4.numpy.delete
函数返回从输入数组中删除指定子数组的新数组。与insert()函数的情况一样，如果未提供轴参数，则输入数组将展开。该函 数接受以下参数：
Numpy.delete(arr, obj, axis)
其中：
•	arr：输入数组
•	obj：可以被切片，整数或者整数数组，表明要从输入数组删除的子数组
•	axis：沿着它删除给定子数组的轴
 
5.numpy.unique
函数返回输入数组中的去重元素数组。该函数能够返回一个元组，包含去重数组和相关索引的数组。索引的性质取决于函数调用中返回参数的类型。
numpy.unique(arr, return_index, return_inverse, return_counts)
其中：
• arr：输入数组，如果不是一维数组则会展开  
• return_index：如果为true，返回输入数组中的元素下标  
• return_inverse：如果为true，返回去重数组的下标，它可以用于重构输入数组  
• return_counts：如果为true，返回去重数组中的元素在原数组中的出现次数
 
08 NumPy - 字符串函数
以下函数用于对dtype为numpy.string_或numpy.unicode_的数组执行向量 化字符串操作。它们基于 Python 内置库中的标准字符串函数。字符数组类(numpy.char)中定义
 
 
 
09 NumPy - 算数函数
NumPy 包含大量的各种数学运算功能。NumPy 提供标准的三角函数，算术运算的函数，复数处理函数等。
•	三角函数
•	舍入函数
•	算数函数
1. NumPy -三角函数
NumPy 拥有标准的三角函数，它为弧度制单位的给定角度返回三角函 数比值。arcsin，arccos，和arctan函数返回给定角度的sin，cos和tan的反三角函数。这些函数的结果可以通过 numpy.degrees()函数通过将弧度制 转换为角度制来验证。
 
2.NumPy -舍入函数
•	numpy.around()这个函数返回四舍五入到所需精度的值
	numpy.around(a,decimals) – a 输入数组
	decimals 要舍入的小数位数。默认值为0。如果为负，整数将四舍五入到小数点左侧的位置
•	numpy.floor() 函数返回不大于输入参数的最大整数。
•	numpy.ceil() 函数返回输入值的上限，大于输入参数的最小整数
 
3.NumPy - 算数运算
用于执行算术运算(如add()，subtract()，multiply()和divide())的输入数组必须具有相同的形状或符合数组广播规则。
•	numpy.reciprocal() 函数返回参数逐元素的倒数。
•	numpy.power() 函数将第一个输入数组中的元素作为底数，计算它与第二个输入数组中相应元素的幂。
•	numpy.mod() 函数返回输入数组中相应元素的除法余数
 
4.NumPy - 统计函数
NumPy 有很多有用的统计函数，用于从数组中给定的元素中查找最小，最大，百分标准差和方差等。
•	numpy.amin() , numpy.amax() 从给定数组中的元素沿指定轴返回最小值和最大值。
•	numpy.ptp() 函数返回沿轴的值的范围(最大值 - 最小值)。
•	numpy.percentile() 表示小于这个值得观察值占某个百分比
•	numpy.percentile(a, q, axis)
	a 输入数组;
	q 要计算的百分位数，在 0 ~ 100 之间;
	axis 沿着它计算百分位数的轴
•	numpy.median() 返回数据样本的中位数。
•	numpy.mean() 沿轴返回数组中元素的算术平均值。
•	numpy.average() 返回由每个分量乘以反映其重要性的因子得到的加权平均值
 
10 排序、搜索和计数函数
NumPy中提供了各种排序相关功能。
•	numpy.sort() 函数返回输入数组的排序副本。numpy.sort(a, axis, kind, order)
	a 要排序的数组;
	axis 沿着它排序数组的轴，如果没有数组会被展开，沿着最后的轴排序;
	kind 默认为'quicksort'(快速排序);
	order 如果数组包含字段，则是要排序的字段
•	numpy.argsort() 函数对输入数组沿给定轴执行间接排序，并使用指定排序类型返回数据的索引数组。这个索引数组用于构造排序后的数组。
•	numpy.lexsort() 函数使用键序列执行间接排序。键可以看作是电子表格中的一列。该函数返回一个索引数组，使用它可以获得排序数据。注意，最后一个键恰好是 sort 的主键。
•	numpy.argmax() 和 numpy.argmin() 这两个函数分别沿给定轴返回最大和最小元素的索引。
•	numpy.nonzero() 函数返回输入数组中非零元素的索引。
•	numpy.where() 函数返回输入数组中满足给定条件的元素的索引。
•	numpy.extract() 函数返回满足任何条件的元素。
 
11 IO文件操作
ndarray对象可以保存到磁盘文件并从磁盘文件加载。可用的 IO 功能有：
•	numpy.save() 文件将输入数组存储在具有npy扩展名的磁盘文件中。
•	numpy.load() 从npy文件中重建数组。
•	numpy.savetxt()和numpy.loadtxt() 函数以简单文本文件格式存储和获取数组数据。
 

