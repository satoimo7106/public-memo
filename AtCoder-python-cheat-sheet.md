
# 目次
- [目次](#目次)
- [入力(str)](#入力str)
- [入力(int)](#入力int)
- [出力(print)](#出力print)
- [if](#if)
- [for](#for)
- [list](#list)
- [set](#set)
- [listやsetなどに対して合計、最大値、最小値を求める](#listやsetなどに対して合計最大値最小値を求める)
- [文字列操作・検索など(join、find、split)](#文字列操作検索などjoinfindsplit)
- [in、not in](#innot-in)
- [スライス](#スライス)
- [ライブラリ](#ライブラリ)
  - [numpy](#numpy)
  - [itertools](#itertools)
- [アルゴリズム](#アルゴリズム)
  - [回文](#回文)
  - [素因数分解](#素因数分解)
  - [累積和](#累積和)
  - [同じ文字が連続する部分文字列を見つける正規表現](#同じ文字が連続する部分文字列を見つける正規表現)
  - [DFS・BFS](#dfsbfs)
- [困ったときに見るリンク](#困ったときに見るリンク)



# 入力(str)

```python
#入力値の例:さかな
s=input()

#入力値の例:さかな まぐろ さんま かつお
s=input().split()

#入力値の例:さかな まぐろ さんま
s1,s2,s3=input().split()

#入力値の例:
#さかな
#まぐろ
str_list=[]
for i in range(n):
    str_list.append(input())

#入力値の例:
#さかな まぐろ さんま
#かつお いか たこ
str_list=[]
for i in range(n):
    str_list.append(input().split())

#文字列を１文字１マスで２次元配列にする
str_list=[]
for i in range(h):
    str_list.append(list(input()))
```

# 入力(int)
```python
#入力値の例:1
n=int(input())

#入力値の例:1 2 3 4 5
n=list(map(int,input().split()))

#入力値の例:1 2
n,m=map(int,input().split())

#入力値の例:
#1
#2
int_list=[]
for i in range(n):
    int_list.append(int(input()))

#入力値の例:
#1 2 3
#4 5 6
int_list=[]
for i in range(n):
    int_list.append(list(map(int,input().split())))
```

# 出力(print)
```python
#文字列を表示
print("ここに表示したい文字列")

#複数の変数の中身を1行で表示
print(s1,s2,s3)

#区切り文字を指定して出力（例はスペース区切りの場合）
#例：0 1 2
ex_list=[0,1,2]
for i in ex_list:
    print(i,end=" ")

#区切り文字を指定してリストなどを出力（例はスペース区切りの場合）
#例：0 1 2
ex_list=[0,1,2]
for i in range(len(ex_list)):
    ex_list[i]=str(i)
print(" ".join(ex_list))

```
参考  

[https://tech-shelf.hatenablog.com/entry/programming/input_output]

[https://www.headboost.jp/python-print-end/]

# if
```python
if 条件式:
    print("A")
elif 条件式:
    print("B")
else:
    print("AとB以外")
```

# for
```python
#n回繰り返す（0~n-1)
for i in range(n):
    print(i)

#初期値nでmまで繰り返す（n~m-1)
for i in range(n,m):
    print(i)

for i in range(n):
    #条件に当てはまるとき処理を1周分スキップ
    if i==2:
        continue
    #条件に当てはまるときループを抜ける
    if i==5:
        break

#xにex_listの中身が順番に入る
for ex in ex_list:
    print(ex)


#複数のリストから同時に要素を取得してループを回す(zip(list,list,...))
for ex1,ex2 in zip(ex_list1,ex_list2):
    print(ex1,ex2)


#逆順にループを回す(range)
for i in reversed(range(n)):
    print(i)

for i in range(n):[::-1]
    print(i)

#逆順にループを回す(list)
for ex in reversed(ex_list):
    print(ex)

for ex in ex_list[::-1]:
    print(ex)


```
参考  
[https://uxmilk.jp/12220]



[https://note.nkmk.me/python-zip-usage-for/]



[https://www.python.ambitious-engineer.com/archives/1757]



[https://uxmilk.jp/8680]



#zip


[https://udon.little-pear.net/python_double_sort/]




# list
```python
#listを空で作成(長さ0)
sample_list=[]

#listを初期値ありで作成
sample_list=["s1","s2"]

#listに変換
sample_list=list(s)

#要素を追加
sample_list.append(s)

#listを参照(n=0~len(sample_list)-1)
print(sample_list[n])

#listの長さを取得
len(sample_list)

#listを逆順にする
sample_list.reverse()
```
参考  
[https://note.nkmk.me/python-reverse-reversed/]


# set
```python
#setを空で作成（長さ0)
sample_set=set()

#setを初期値ありで作成
sample_set={"s1","s2"}

#setに変換
sample_set=set(s)

#要素を追加
sample_set.add(s)

```
参考  
[https://www.javadrive.jp/python/set/index1.html]



# listやsetなどに対して合計、最大値、最小値を求める
```python
#合計
sum()

#最大値
max()

#最小値
min()

```
# 文字列操作・検索など(join、find、split)
```python
#文字列を逆向きにする
reversed_str=''.join(list(reversed(s)))

#文字列に対して特定の文字の位置を取得(0~)
s_index=s.find("example")

#listを文字列にする（この場合は区切り文字なし）
''.join(ex_list)

#文字列をlistにする（引数なしの場合は空白文字で区切る）
s.split()
```
参考  
[https://note.nkmk.me/python-reverse-reversed/]

[https://note.nkmk.me/python-str-search/]

[https://www.headboost.jp/python-strings-into-a-list/]






# in、not in
```python
#xがyに含まれていたらTrue
if x in y:
    print("")

#xがyに含まれていなかったらTrue
if x not in y:
    print("")
```
参考  
[https://note.nkmk.me/python-in-basic/]



# スライス
※スライスの":"の後ろに設定する数字の部分はスライスの範囲に含まれないので注意が必要。(例:[0:5]にした場合0~4(5-1)までが範囲となる）
```python
#すべて
ex_list[:]
#0~4番目
ex_list[:5]
#5~（一番後ろ）番目
ex_list[5:]


#2次元配列(※numpy配列)
#0行目のみ
ex_list[0,:]
#0列目のみ
ex_list[:,0]
```
参考  
[https://note.nkmk.me/python-slice-usage/]

[https://it-ojisan.tokyo/python-slice/]


# ライブラリ
使ったことがあるライブラリ
## numpy
```python
#インポート
import numpy as np

#listをnumpy配列にする
np_list=np.array(sample_list)

#numpy配列をlistにする
sample_list=tolist(np_list)

```
参考  
[https://note.nkmk.me/python-numpy-list/]

## itertools
```python
#インポート
import itertools

#順列を生成
p = itertools.permutations(listやsetなど, 選択する個数)

#順列を列挙
for p in itertools.permutations(listやsetなど, 選択する個数):
    print(p)
```
参考  

[https://qiita.com/anmint/items/37ca0ded5e1d360b51f3]

[https://note.nkmk.me/python-math-factorial-permutations-combinations/]


[https://qiita.com/Mohrey/items/b0afc8edc5fed742b68a]




# アルゴリズム
使ったことがあるアルゴリズム

## 回文
[https://tjkendev.github.io/procon-library/python/string/manacher.html]

[https://qiita.com/Shawna/items/17ed870cd4c8c0f1f478]

## 素因数分解

[https://note.nkmk.me/python-prime-factorization/]

## 累積和

[https://note.nkmk.me/python-itertools-accumulate/]


[https://qiita.com/drken/items/56a6b68edef8fc605821#2-2-%E7%B4%AF%E7%A9%8D%E5%92%8C%E3%82%92%E8%A6%96%E8%A6%9A%E7%9A%84%E3%81%AB%E7%90%86%E8%A7%A3%E3%81%99%E3%82%8B]

## 同じ文字が連続する部分文字列を見つける正規表現

[https://qiita.com/norioc/items/324d9210ae2db29d08e6]

## DFS・BFS

[https://amateur-engineer-blog.com/dfs-bfs/]




# 困ったときに見るリンク

[https://algo-logic.info/how-to-think-cp/#]


[https://qiita.com/sano192/items/e63d7a794b621b5d5ec6]

[https://qiita.com/H20/items/3de3f298b7c075fa5925]






