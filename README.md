# download-large-dataset

以Chicago taxi trip数据为例：

1.下载：可以通过数据商的api（通常需要token或者有速度限制）或者直接export的形式下载（在这里效率更高🤣，专治各种花里胡哨）

2.大概是70多个G，2亿多条数据，分成了200个csv文件，直接合并会让内存爆炸。可以用polar读取一组csv，转换成parquet临时储存，只至所有csv都被转成parquet（一般来说其实到这里就可以了，如果PI不是一定要dta的话）

3.挨个读取parquet，再将这些转成dta，再去stata中合并（stata为数不多的优点）
