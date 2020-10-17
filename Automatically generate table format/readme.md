# Automatically generate table format

所用到的公式:	
- 如果是0就	=IF((B2-A2)=0,"",B2-A2)或儲存格C2：=IF(B2-A2,B2-A2,"")
- 如果是錯誤就空白	IFERROR(B2/A2,"")
- 如果是boolean就轉成bit	"=IF(IFERROR(MID(D2,1,(FIND("(",D2)-1)),D2)="boolean","bit",IFERROR(MID(D2,1,(FIND("(",D2)-1)),D2))"
