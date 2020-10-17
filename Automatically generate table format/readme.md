# Automatically generate table format
---

### 效果:
使用這EXCEL做資料庫的表格，大約可以使4/5的時間，但因為只有個人使用，沒有優化的很完全，大約是還不錯而已。

### 使用方法:
- 在網路上選擇「來源TABLE、欄位、新欄位名稱及資料欄格式
![](https://i.imgur.com/QsC6M2y.png)
- 貼在做表格的程式綠色欄的地方
![](https://i.imgur.com/HMbgrLN.png)
- 複製白色這個區塊

![](https://i.imgur.com/vrtgS2M.png)

- 貼上後小修即可

```
"USE [KL]
GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Category]("
[ID][nvarchar](100) NULL,
[Name][nvarchar](200) NULL,
[Published][bit] NULL,
[ParentCategoryId][int] NULL,
[MetaTitle][nvarchar](400) NULL,
[MetaDescription][nvarchar](Max) NULL,
[MetaKeywords][nvarchar](400) NULL,
[ShowOnHomePage][bit] NULL,
[][0] NULL,
") ON [PRIMARY]
GO"
```

### 而資料表的新增
由MS-SQL自動GEN出來再修改就好了。





### 所用到的公式:	
- 如果是0就	=IF((B2-A2)=0,"",B2-A2)或儲存格C2：=IF(B2-A2,B2-A2,"")
- 如果是錯誤就空白	IFERROR(B2/A2,"")
- 如果是boolean就轉成bit	"=IF(IFERROR(MID(D2,1,(FIND("(",D2)-1)),D2)="boolean","bit",IFERROR(MID(D2,1,(FIND("(",D2)-1)),D2))"
