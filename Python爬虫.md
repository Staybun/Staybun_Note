### Python爬虫

-   ![image-20250307164243837](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20250307164243837.png)

![image-20250307164704053](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20250307164704053.png)

-   检查r.text时：看**meta，charset**

​	![image-20250307191257934](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20250307191257934.png)

![image-20250307191343642](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20250307191343642.png)

![image-20250307191503380](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20250307191503380.png)

```python
import requests        ###demo1
from bs4 import BeautifulSoup

url = "http://www.crazyant.net"

response = requests.get(url)
soup = BeautifulSoup(response.text, "html.parser")
notes = soup.find_all("h2",class_='entry-title')
for note in notes:
    link=note.find('a')
    print(link['href'],link.get_text())
```


