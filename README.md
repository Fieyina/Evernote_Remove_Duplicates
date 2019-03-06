# evernote_remove_duplicates
印象笔记去重  
## 关注主线
1. 访问以下网站获取 token，填入 py 文件的 token 处  
https://app.yinxiang.com/api/DeveloperToken.action
2. 将 check 改为你的一个笔记本名称，推荐新建一个笔记本同时加入一些重复笔记，检验程序是否可以正常运行
3. 将 check 改为 None
4. 运行 py 文件，完成去重
## 注意事项
***务必仔细阅读以下注意事项，以防错删***
1. 笔记本**不可重名**
2. 每个笔记本内的笔记**数目不得多于 250 个**
3. API 有调用频率限制，当抛出 EDAMSystemException 异常时，rateLimitDuration 表示离刷新计数的时间间隔（秒）
## 方法
#### get_notebook_list（API）
调用 API，获得**笔记本数据集**
#### search_note（笔记本名称，笔记本数据集）
接受笔记本名称，获得该笔记本下的**笔记数据集**
#### get_note_list（笔记本数据集，笔记本名[可选]）
接受**笔记本数据集**，获得**笔记数据集**  
可选参数用于检验程序是否正常运行
#### writer_to_excel（笔记数据集，excel 文件名）
接受**笔记数据集**导出备查 excel
## 数据结构
#### 笔记本数据集
columns = ['tag', 'name', 'guid']
#### 笔记数据集
columns=['name', 'guid']
## 参考文献
1. 印象笔记开发者文档  
https://dev.yinxiang.com/doc/  
2. 使用 Python 操作 Evernote - 简书  
https://www.jianshu.com/p/bda26798f3b3  
3. Github / EvernoteController  
https://github.com/littlecodersh/EasierLife/tree/master/Programs/Evernote  
