---
layout: post
title: 正则表达式常用符号
description: 
date: 2018-09-09
tags: [Regex]
---


# Regex

## 元字符

| 符号  | 说明                     |
| :---: | ------------------------ |
| .     | 除换行符以外任意字符     |
| \w    | 字母、数字或下划线       |
| \W    | 非字母、数字或下划线     |
| \s    | 任意空白符               |
| \S    | 非空白符                 |
| \d    | 数字                     |
| \D    | 非数字                   |
| \b    | 单词开始或结束           |
| \B    | 不是单词开始或结束的位置 |
| ^     | 字符串的开始             |
| $     | 字符串的结束             |
| [^ae] | 除ae外的任意字符         |

<!--more-->

## 字符转义

当要匹配元字符中定义的符号时，需要用反斜杠转义，比如\\$匹配\$号

## 重复  

| 符号  | 说明           |
| :---: | -------------- |
| *     | 重复0次或多次  |
| +     | 重复一次或多次 |
| ?     | 重复0次或1次   |
| {n}   | 重复n次        |
| {n,}  | 重复n次或多次  |
| {n,m} | 重复n到m次     |

## 匹配指定范围的字符

用中括号[]来指定匹配的字符范围，比如：  
[a-z0-9A-Z]匹配字母或数字  
[aeiou]匹配列出的元音字母  

## 分组

- 分组用小括号表示，小括号中的表达式匹配到的文本，就是分组捕获到的内容，可在表达式或其它程序中做进一步处理  
- 每个分组自动拥有一个组号，从1开始编号(分组0为整个表达式)，如\\1表示第一个分组，可以用于在后续表达式中重复搜索前面的分组匹配到的文本,比如表达式"\b(\w+)\b\s+\1\b"可以用于匹配重复的单词，其中"\b(\w+)\b"用于匹配一个单词，该单词位于分组1，"\s+"匹配一个或多个空白符，"\1"用于重复匹配前面匹配到的单词
- 也可以自己指定表达式的**组名**，用法为: (?<group_name>\w+)，尖括号也可以换成单引号。要引用这个分组捕获的内容，可以用\k<group_name>  
