# 微信公众号文章爬虫

步骤:

1. 从微信公众号平台获取微信公众所有文章的url

2. 登录微信PC端获取文章的阅读数、评论等信息

具体可以参考: [微信公众号爬虫](http://blog.csdn.net/wnma3mz/article/details/78570580)

## API操作

```python
# 导入模块
from wechatarticles import OfficialWeChat
from wechatarticles import LoginWeChat

# 添加cookie、token、nickname为需要爬取的公众号
cookie = yourcookie
token = token
nickname = nickname

# 实例化爬取对象
test = OfficialWeChat(token, cookie)
# 获取公众号文章总数
articles_sum = test.totalNums(nickname)
# 获取公众号部分文章信息
artiacle_data = test.get_articles(nickname, begin="10", count="5")
# 获取公众号的一些信息
officical_info = test.get_official_info(nickname)
# 保存数据为txt格式
test.save_txt("test.txt", artiacle_data)
# 保存数据为sqlite3
test.save_sqlite("test.db", "test", artiacle_data)
```

```python
# 输出
print("articles_sum:", articles_sum)
print("artcles_data:")
pprint(artiacle_data)
print("officical_info:")
pprint(officical_info)
```

## TO-DO

1. 模拟登录微信PC端
