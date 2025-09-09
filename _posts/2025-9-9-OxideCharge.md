
---
layout: post
title: "氧化层电荷仿真"
date:   2025-9-9
tags: [TCAD, 学习]
comments: true
author: lxjia3
---

# Sentaurus TCAD 

Source:Sentaurus sdevice_ug CHAPTER 17 Traps and Fixed Charges

## 缺陷介绍
缺陷研究意义：缺陷提供掺杂，增强复合并且提高通过绝缘层的漏电流。本章节模型介绍了缺陷上的占位和存储电荷。
Sentaurus提供了几种缺陷类型和能量分布类型，并提供了不同捕获和耗散速率，对于块体和表面都有用。也有一个用于绝缘层固定电荷的模型。

## 绝缘层固定电荷
Sentaurus Device 提供了适用于体内和表面的绝缘层固定电荷，在_Physice_中使用_Charge_开启，示例：
```
Physics (Material="Oxide"){
   Charge (
   (<charge_specification>)
   (<charge_specification>)
   )
 }
```
语法使用类似_MaterialInterface, Region, and RegionInterface_，具体参数总结在Table 276中。
当只是用一个参数时，可以省略内部括号：
```
Physics (Material="Oxide"){
 Charge (
 <charge_specification>
 )
 }
```

对于块体材料，只需要一个相关关键词：_Conc_,其单位为 _q_cm<sup>-3</sup>

表面的固定电荷可以写成高斯或者均匀分布：
```
 Charge([Gaussian | Uniform]
 Conc = <float>
 SpaceMid = <vector>
 SpaceSig = <vector>
 )
```
关键词Conc指定最大表面电荷密度：σ<sub>0</sub>(_q_cm<sup>-2</sup>),SpaceMid 和 SpaceSig 指定电荷分布中心和宽度，可以在均匀分布中设置，但在高斯分布中必须指定。





