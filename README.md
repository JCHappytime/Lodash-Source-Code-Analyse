# Lodash-Source-Code-Analyse

## 目的

本库的目的时对lodash源码进行分析，剖析给我们提供便利的lodash是如何实现这些功能的。

## 安装

npm i --save lodash / yarn add lodash

## 目录

- [1. _chunk](#1-_chunk)


#### 1. _chunk
```
_.chunk(array, [size=1])
参数：
- array：需要处理的数组
- [size=1]每个数组区块的长度
```
作用：将数组array拆分成多个size长度的区块，并将这些区块组成一个新的数组。如果array无法被分割成全部等长的区块，那么最后剩余的元素将组成一个区块。
