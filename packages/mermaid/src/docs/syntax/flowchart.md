graph TD;
  subgraph 图书管理菜单
    Menu((==== 图书管理系统 ====))
    AddBook(添加图书)
    BorrowBook(借阅图书)
    ReturnBook(归还图书)
    DisplayBooks(查看图书)
    DisplayRecords(查看借阅记录)
    DisplayReaders(查看读者信息)
    AddReader(添加读者信息)
    DeleteBook(删除图书)
    DeleteReader(删除借阅人)
    Exit(退出)
  
    Menu -->|1| AddBook
    Menu -->|2| BorrowBook
    Menu -->|3| ReturnBook
    Menu -->|4| DisplayBooks
    Menu -->|5| DisplayRecords
    Menu -->|6| DisplayReaders
    Menu -->|7| AddReader
    Menu -->|8| DeleteBook
    Menu -->|9| DeleteReader
    Menu -->|0| Exit

  subgraph 图书操作
    BookInfo[图书信息结构体]
    AddBook -->|输入图书信息| BookInfo
    BorrowBook -->|查找并减少库存| BookInfo
    ReturnBook -->|查找并增加库存| BookInfo

  subgraph 借阅记录操作
    RecordInfo[借阅记录结构体]
    BorrowBook -->|创建借阅记录| RecordInfo
    ReturnBook -->|更新借阅记录| RecordInfo
    DisplayRecords --> RecordInfo

  subgraph 读者操作
    ReaderInfo[读者信息结构体]
    AddReader -->|输入读者信息| ReaderInfo
    BorrowBook -->|查找读者信息| ReaderInfo
    DeleteReader -->|删除读者信息| ReaderInfo
    DisplayReaders --> ReaderInfo
