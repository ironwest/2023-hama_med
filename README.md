## 講義に利用したパッケージ

* tidyverse 1.3.2
* gtsummary 1.6.1
* DiagrammeR 1.0.9


## 講義に推奨する環境

* Rバージョン4.2.1 以降（日本語関係のトラブルが圧倒的に4.2.0以降で少なくなったので、なるべく最新のRを利用してください）

* RStudio 2022.07.1+554 "Spotted Wakerobin" Release 以降

## RとRStudioのインストール方法

* [ネットで見つけた記事](https://multivariate-statistics.com/2022/10/21/r-programming-install/):こちら、大変分かりやすい記事でした。


* [こちらのオンラインコース](https://www.udemy.com/course/data-analysis-by-r-for-medical-profession/)にある、「導入と準備」を無料プレビューできるようにしてあるので、そちらを参考にしていただいても良いと考えます。

## Rに全くふれたことがない場合

[こちらのオンラインコース](https://www.udemy.com/course/data-analysis-by-r-for-medical-profession/)のセクション２で無料視聴できる内容は押さえておいていただくと、ついてきやすくなるかもしれません。


## 講義開始前に次のコードがエラーなく動いていることの確認を推奨します

```{r}
library(tidyverse)
library(DiagrammeR)
library(gtsummary)

 #これらのパッケージがなければ、install.packages("tidyverse")などとしてインストールしてください。


d <- tibble(a = rnorm(1000,0,10),
            b = 10 + a*3 + rnorm(1000,0,10))

d
```


```{r}
DiagrammeR::grViz("digraph{a -> b}")
```


```{r}
mod1 <- lm(b~a,d)
gtsummary::tbl_regression(mod1)
```

