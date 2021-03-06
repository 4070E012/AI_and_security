# Web安全之机器学习入门
```
https://github.com/duoergun0729/1book
```
```
第1章 通向智慧安全的旅程 1
1.1 人工智慧、機器學習與深度學習 1
1.2 人工智慧的發展 2
1.3 國內外網路安全形勢 3
1.4 人工智慧在安全領域的應用 5
1.5 演算法和資料的辯證關係 9
1.6 本章小結 9
參考資源 10

第2章 打造機器學習工具箱 11
2.1 Python在機器學習領域的優勢 11
2.1.1 NumPy 11
2.1.2 SciPy 15
2.1.3 NLTK 16
2.1.4 Scikit-Learn 17
2.2 TensorFlow簡介與環境搭建 18
2.3 本章小結 19
參考資源 20

第3章 機器學習概述 21
3.1 機器學習基本概念 21
3.2 資料集 22
3.2.1 KDD 99數據 22
3.2.2 HTTP DATASET CSIC 2010 26
3.2.3 SEA資料集 26
3.2.4 ADFA-LD資料集 27
3.2.5 Alexa功能變數名稱數據 29
3.2.6 Scikit-Learn資料集 29
3.2.7 MNIST資料集 30
3.2.8 Movie Review Data 31
3.2.9 SpamBase資料集 32
3.2.10 Enron資料集 33
3.3 特徵提取 35
3.3.1 數字型特徵提取 35
3.3.2 文本型特徵提取 36
3.3.3 數據讀取 37
3.4 效果驗證 38
3.5 本章小結 40
參考資源 40

第4章 Web安全基礎 41
4.1 XSS攻擊概述 41
4.1.1 XSS的分類 43
4.1.2 XSS特殊攻擊方式 48
4.1.3 XSS平臺簡介 50
4.1.4 近年典型XSS攻擊事件分析 51
4.2 SQL注入概述 53
4.2.1 常見SQL注入攻擊 54
4.2.2 常見SQL注入攻擊載荷 55
4.2.3 SQL常見工具 56
4.2.4 近年典型SQL注入事件分析 60
4.3 WebShell概述 63
4.3.1 WebShell功能 64
4.3.2 常見WebShell 64
4.4 僵屍網路概述 67
4.4.1 僵屍網路的危害 68
4.4.2 近年典型僵屍網路攻擊事件分析 69
4.5 本章小結 72
參考資源 72

```
### 第5章 K近鄰演算法 74

5.1 K近鄰演算法概述 74

5.2 示例：hello world！K近鄰 75
http://scikit-learn.org/stable/modules/generated/sklearn.neighbors.NearestNeighbors.html
```
print(__doc__)

from sklearn.neighbors import NearestNeighbors
import numpy as np


X = np.array([[-1, -1], [-2, -1], [-3, -2], [1, 1], [2, 1], [3, 2]])
nbrs = NearestNeighbors(n_neighbors=2, algorithm='ball_tree').fit(X)

distances, indices = nbrs.kneighbors(X)

print distances
print indices

print nbrs.kneighbors_graph(X).toarray()
```
KNN監督學習
```

X = [[0],[1],[2],[3]]  
y = [0, 0, 1 ,1]
from sklearn.neighbors import KNe1ghborsClassifier
neigh = KNe1ghborsClassifier(n_neighbers=3)
neigh.fit(X,y)
print(neigh_predict([[1.1]]))
print(neigh_predict_prob([[0.9]]))
```

5.3 示例：使用K近鄰演算法檢測異常操作（一） 76

```
測試資料集: http://www.schonlau.net/
Masquerading User Data

5-2.py

```

```
5.4 示例：使用K近鄰演算法檢測異常操作（二） 80
5.5 示例：使用K近鄰演算法檢測Rootkit 81
5.6 示例：使用K近鄰演算法檢測WebShell 83
參考資料 
```
### 第6章 決策樹與隨機森林演算法 87
```
6.1 決策樹演算法概述 87
6.2 示例：hello world！決策樹 88
6.3 示例：使用決策樹演算法檢測POP3暴力破解 89
6.4 示例：使用決策樹演算法檢測FTP暴力破解 91
6.5 隨機森林演算法概述 93
6.6 示例：hello world！隨機森林 93
6.7 示例：使用隨機森林演算法檢測FTP暴力破解 95
參考資源 96
```
### 第7章 樸素貝葉斯演算法 97
```
7.1 樸素貝葉斯演算法概述 97
7.2 示例：hello world！樸素貝葉斯 98
7.3 示例：檢測異常操作 99
7.4 示例：檢測WebShell（一） 100
7.5 示例：檢測WebShell（二） 102
7.6 示例：檢測DGA功能變數名稱 103
7.7 示例：檢測針對Apache的DDoS攻擊 104
7.8 示例：識別驗證碼 107
參考資源 108
```
### 第8章 邏輯回歸演算法 109
```
8.1 邏輯回歸演算法概述 109
8.2 示例：hello world！邏輯回歸 110
8.3 示例：使用邏輯回歸演算法檢測Java溢出攻擊 111
8.4 示例：識別驗證碼 113
參考資源 114
```
### 第9章 支援向量機演算法 115
```
9.1 支援向量機演算法概述 115
9.2 示例：hello world！支持向量機 118
```
```
print(__doc__)

import numpy as np
import matplotlib.pyplot as plt
from sklearn import svm

# we create 40 separable points
np.random.seed(0)
X = np.r_[np.random.randn(20, 2) - [2, 2], np.random.randn(20, 2) + [2, 2]]
Y = [0] * 20 + [1] * 20

# fit the model
clf = svm.SVC(kernel='linear')
clf.fit(X, Y)

# get the separating hyperplane
w = clf.coef_[0]
a = -w[0] / w[1]
xx = np.linspace(-5, 5)
yy = a * xx - (clf.intercept_[0]) / w[1]

# plot the parallels to the separating hyperplane that pass through the
# support vectors
b = clf.support_vectors_[0]
yy_down = a * xx + (b[1] - a * b[0])
b = clf.support_vectors_[-1]
yy_up = a * xx + (b[1] - a * b[0])

# plot the line, the points, and the nearest vectors to the plane
plt.plot(xx, yy, 'k-')
plt.plot(xx, yy_down, 'k--')
plt.plot(xx, yy_up, 'k--')

plt.scatter(clf.support_vectors_[:, 0], clf.support_vectors_[:, 1],
            s=80, facecolors='none')
plt.scatter(X[:, 0], X[:, 1], c=Y, cmap=plt.cm.Paired)

plt.axis('tight')
plt.show()
```
9.3 示例：使用支援向量機演算法識別XSS 120
```
9-2.py
```
9.4 示例：使用支援向量機演算法區分僵屍網路DGA家族 124
```
9-3.py
9.4.1 資料搜集和資料清洗 124
9.4.2 特徵化 125
9.4.3 模型驗證 129

參考資源 130
```
### 第10章 無監督學習演算法:K-Means與DBSCAN演算法 131

```
10.1 K-Means演算法概述 131
10.2 示例：hello world！K-Means 132
10-1.py
```
```
import numpy as np
import matplotlib.pyplot as plt

from sklearn.cluster import KMeans
from sklearn.datasets import make_blobs

def show_kmeans():
    print(__doc__)
    plt.figure(figsize=(12, 12))

    n_samples = 1500
    random_state = 170
    X, y = make_blobs(n_samples=n_samples, random_state=random_state)
    y_pred = KMeans(n_clusters=3, random_state=random_state).fit_predict(X)


    plt.subplot(221)
    plt.scatter(X[:, 0], X[:, 1], c=y_pred)
    plt.title("hello word!")

    plt.show()

if __name__ == '__main__':
    show_kmeans()
```

```

10.3 示例：使用K-Means演算法檢測殭屍網路DGA功能變數名稱 133
10-2.py

10.4 DBSCAN演算法概述 135
10.5 示例：hello world！DBSCAN 135
10-3.py

參考資源 137
```
### 第11章 Apriori與FP-growth演算法 138

```
11.1 Apriori演算法概述 138
11.2 示例：hello world！Apriori 140
11.3 示例：使用Apriori演算法挖掘XSS相關參數 141
11.4 FP-growth演算法概述 143
11.5 示例：hello world！FP-growth 144
11.6 示例：使用FP-growth演算法挖掘疑似僵屍主機 145
參考資源 146
```
### 第12章 隱式瑪律可夫演算法 147
```
12.1 隱式瑪律可夫演算法概述 147
Hidden Markov model 
https://en.wikipedia.org/wiki/Hidden_Markov_model

需額外安裝HMM
pip install hmmlearn

12.2 hello world! 隱式瑪律可夫 148
12-1.py

12.3 示例：使用隱式瑪律可夫演算法識別XSS攻擊（一） 150
12-2.py
12.4 示例：使用隱式瑪律可夫演算法識別XSS攻擊（二） 153
12.5 示例：使用隱式瑪律可夫演算法識別僵屍網路DGA功能變數名稱 159
參考資源 162
```
### 第13章 圖演算法與知識圖譜 163
```
13.1 圖演算法概述 163
13.2 示例：hello world！有向圖 164
13.3 示例：使用有向圖識別WebShell 169
13.4 示例：使用有向圖識別僵屍網路 173
13.5 知識圖譜概述 176
13.6 示例：知識圖譜在風控領域的應用 177
13.6.1 檢測疑似帳號被盜 178
13.6.2 檢測疑似撞庫攻擊 179
13.6.3 檢測疑似刷單 181
13.7 示例：知識圖譜在威脅情報領域的應用 183
13.7.1 挖掘後門檔潛在聯繫 184
13.7.2 挖掘功能變數名稱潛在聯繫 185
參考資源 187
```
### 第14章 神經網路演算法 188
```
14.1 神經網路演算法概述 188
14.2 示例：hello world！神經網路 190
14.3 示例：使用神經網路演算法識別驗證碼 190
14.4 示例：使用神經網路演算法檢測Java溢出攻擊 191
參考資源 194
```
### 第15章 多層感知機與DNN演算法 195
```
15.1 神經網路與深度學習 195
15.2 TensorFlow程式設計模型 196
15.2.1 操作 197
15.2.2 張量 197
15.2.3 變數 198
15.2.4 會話 198
15.3 TensorFlow的運行模式 198
15.4 示例：在TensorFlow下識別驗證碼（一） 199
15.5 示例：在TensorFlow下識別驗證碼（二） 202
15.6 示例：在TensorFlow下識別驗證碼（三） 205
15.7 示例：在TensorFlow下識別垃圾郵件（一） 207
15.8 示例：在TensorFlow下識別垃圾郵件（二） 209
參考資源 210
```

### 第16章 迴圈神經網路演算法(RNN) 212
```
https://brohrer.mcknote.com/zh-Hant/how_machine_learning_works/how_rnns_lstm_work.html

16.1 迴圈神經網路演算法概述 212
16.2 示例：識別驗證碼 213
16-1.py

16.3 示例：識別惡意評論 216
16-2.py
16-3.py

16.4 示例：生成城市名稱 220
16-4.py

16.5 示例：識別WebShell 222
LSTM
16-5.py

16.6 示例：生成常用密碼 225
16-6.py

16.7 示例：識別異常操作 227
16-7.py

參考資源 230
```

### 第17章 卷積神經網路演算法(CNN) 231
```
17.1 卷積神經網路演算法概述 231
17.2 示例：hello world！卷積神經網路 234
17-1.py

17.3 示例：識別惡意評論 235
17-2.py

17.4 示例：識別垃圾郵件 237
17-3.py
```
