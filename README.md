# Lodash-Source-Code-Analyse

## 目的

本库的目的时对lodash源码进行分析，剖析给我们提供便利的lodash是如何实现这些功能的。

## 安装

npm i --save lodash / yarn add lodash

## 目录

- [1. _chunk](#1-_chunk)
- [2. _slice](#2-_slice)


#### 1. _chunk
```
_.chunk(array, [size=1])
参数：
- array：需要处理的数组
- [size=1]每个数组区块的长度
```
作用：将数组array拆分成多个size长度的区块，并将这些区块组成一个新的数组。如果array无法被分割成全部等长的区块，那么最后剩余的元素将组成一个区块。

使用示例：
```
_.chunk([1, 2, 3, 4, 5], 2)    // => [[1, 2], [3, 4], [5]]
_.chunk([1, 2, 3, 4, 5, 6], 3)    // => [[1, 2, 3], [4, 5, 6]]

```
源码分析：

```
function chunk(array, size=1) {
  size = Math.max(toInteger(size), 0);
  const length = array === null ? 0 : array.length;
  if (!length || size < 1) {
    return [];
  }
  let index = 0;
  let resIndex = 0;
  const result = new Array(Math.ceil(length / size));
  
  while (index < length) {
    result[resIndex++] = this.slice(array, index, (index += size));
  }
  return result;
}
```
这里slice()方法的源码见: [2. _slice](#2-_slice)

#### 2. _slice

```
_.slice(array, [start=0], [end=array.length])
参数：
- array: 待裁剪的数组;
- [start=0]: 开始位置;
- [end=array.length]: 结束位置;
```
作用：裁剪数组array，从start位置开始到end结束，但不包括end本身的位置。

使用示例：
```
_.slice([1, 2, 3, 4, 5], 2, 3)    // => [3]
_.slice([1, 2, 3, 4, 5, 6], 3)    // => [4, 5, 6]

```
源码分析：

```

```



























































