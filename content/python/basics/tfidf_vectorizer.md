```python
import pandas as pd
from sklearn.feature_extraction.text import TfidfVectorizer
```


```python
tfidf_vectorizer = TfidfVectorizer()
```


```python
def feature_extraction(msg):
    
    mat = pd.DataFrame(tfidf_vectorizer.fit_transform(msg).toarray(),columns=tfidf_vectorizer.get_feature_names(),index=None)
    return mat
```
