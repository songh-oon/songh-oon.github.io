---
layout : post
title : "Python Statistic Basic"
menu : 공부
author :
tags: python statistic
comments : False
published: True

---


### SPSS보다 Python을 쓸 테야

말 그대로 굳이 spss 쓸 필요가 없는 세상이라고 느껴서, spss에서 쓰는 기능을 간단하게 python을 이용하여 실행해 보려고 한다.

당연하게도, 구글과 chatGPT의 도움으로 모든 걸 해결할 수 있다.

---

<br>

##### 환경

우선 환경은 뭐 다양하게 이용할 수 있겠지만, 많은 기능이 필요없기 때문에 jupyter notebook이나 anaconda, 혹은 VS code 등까지는 이용할 필요가 없다고 생각했다. 

그래서 그냥 iterm에서 vim을 켰다.

그리고 버전이나 환경관리를 위해 venv 를 이용하여 virtual invironment에서 python 및 라이브러리들을 이용했다.

주로 이용한 라이브러리들은 다음과 같다.
`pandas` `scipy.stats` `statsmodels` `pingouin` `numpy` `openpyxl` `pyreadstat` 



---
<br>

##### 활용예시

다음은 사회과학 영역에서 많이 쓰이는 통계들을 어떻게 할 수 있는지 찾아보았다.

#### 1. Frequency Analysis
```
data['your_column'].value_counts()

# value_contents() for categorical data 
# hist() for numerical data
```
#### 2.  Cronbach's Alpha(Reliability Analysis)
```
import pingouin as pg

# Cronbach's Alpha
cronbach_alpha = pg.cronbach_alpha(data[['item1', 'item2', 'item3']])
```
#### 3. Pearson Correlation Analysis
```
from scipy.stats import pearsonr

correlation, p_value = pearsonr(data['var1'], data['var2'])
```
#### 4. Regression Analysis
```
import statsmodels.api as sm

X = data[['predictor1', 'predictor2']]
X = sm.add_constant(X)  # Adds a constant term to the model
y = data['outcome']

model = sm.OLS(y, X).fit()
print(model.summary())
```
#### 5. T-tests
```
from scipy.stats import ttest_ind

t_stat, p_value = ttest_ind(data['group1'], data['group2'])
```
<br>

>혹시나 문제가 있다면 추후 수정될 예정

