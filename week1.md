###### tags: `影像處理 DIP`
# 第一堂課 - 影像處理 digital image processing (DIP)

### 期中(筆試)、期末(專案 or 報告)

取樣越多，pixel越高，像是1080*720
![](https://i.imgur.com/VwSbPGz.png)
#### Quantization 量化：
#### 把某範圍內的變化用數值表現出來的過程。例如把水的凝固點到沸點之間畫分成一百個相同的間隔，每間隔稱為一度，而把測得的溫度用整數值表示。如三十八度、四十二度、一百度。後來在社會科學上，描述觀察的現象，用數值表達並加運算，也稱為「量化」。
#### 這邊將圖內黑到白分為8 ($2^3$)個顏色


#### 為什麼說 8bits 等於 1byte 呢？
#### 因為量化數目 (黑到白切多少等分)，越多越好，切到 256 時 ($2^8$)，將會看不出來有切割

#### 期中考第一題(量化、取樣)：![](https://i.imgur.com/mzFFx0y.png)
畫出右圖


### 彩色影像 color image
最基本的是 R(0~255)GB，共 3 bytes
選這三色是因為人類對這三色感受比較強烈，24bits全彩，2的24次(一千六百多萬)
### 灰階影像 gray(-level) image
預設為256色的，剛好是 8 bits，1 byte
白色 = 255，黑色 = 0 
### 黑白影像 binary image、mono image
只需要 1 bit 就可以儲存
白色 = 1，黑色 = 0 ，高的指白色，低的指黑色

## 課本第二章前的內容

下載 ANACONDA [點我進官網](https://www.anaconda.com/distribution/)
下載 ANACONDA 後點開 Spyder(Anaconda3) 老師用的編譯器

## 安裝 OpenCV
![](https://i.imgur.com/vYhDoWg.png)

兩種方法：
1. 點開 Anaconda Navigator 點選 Environments 選 not installed 選 OpenCV 安裝
2. 一樣點開 Anaconda Navigator 點選 Environments 再 base(root) 點選 Open Terminal 
輸入> 
`pip install opencv-python`
安裝完會出現以下字樣
`Successfully installed opencv-python-x.x.x`

[OpenCV —在Windows中安裝 OpenCV-python](https://medium.com/@airwaves/opencv-%E5%9C%A8windows%E4%B8%AD%E5%AE%89%E8%A3%9D-opencv-python-295ae092ca57)

[Python 與 OpenCV 基本讀取、顯示與儲存圖片教學](https://blog.gtwang.org/programming/opencv-basic-image-read-and-write-tutorial/)


[python3+opencv 图像通道的分离（split（）函数）和合并（merge（）函数） 完整教學](https://blog.csdn.net/u014453898/article/details/80715121) (我找你找的好苦啊，但是看了卻是一知半解)

![](https://i.imgur.com/wFzNH6G.png)

#### 引入 OpenCV 的模組
`import cv2`

#### 引入 Numpy 的模組
`import numpy as np`
`將 numpy 重新命名為 NP`

### cv2.imread 將圖片讀入，讀進來的資料，會儲存成一個 NumPy 的陣列
用法為 img = cv2.imread("圖片路徑")

NumPy 陣列的前兩個維度分別是圖片的高度與寬度，第三個維度則是圖片的 channel（RGB 彩色圖片的 channel 是 3，灰階圖片則為 1）

### cv2.imshow 顯示圖片
用法為 cv2.imshow("給新的名字", 將上面的名稱放入"img")

### cv2.waitkey(0)
點選任意圖片，按下空白鍵就可以執行下面一行
cv2.detroyAllWindows()