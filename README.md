# search-center
Search Center  Based Lucene<br>
提供搜索接口的服务中心。<br>
将autoDanime和blog项目的搜索模块移动于此。<br>
建立了搜索索引的类每次更改，都需要更新索引，以保持搜索内容的正确性。这种做法耗时，且稳定性不高<br>
所以将其他项目中的索引的建立&更新&删除以及搜索服务接口统一移动到此项目。<br>
具体设计实现：<br>
----
1.使用canal 获取mysql的binlog日志，获得数据库的实时更新后，修改索引。<br>
2.使用dubbo对外提供 搜索服务接口。这样其他项目就不需要考虑搜索的实现,且实现了搜索的资源可在不同应用相互共用。<br>

Update：使用spring boot重新实现搜索中心(search-provider-springboot)。原provider停用(search-provider)。






