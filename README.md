# 發想

最近在看Kaggle GenAI 的內容，  
裡面談到了對於RAG 的實作應用，  
因為自己剛好也有在用Obsidian 筆記軟體，  
想到似乎可以把自己的筆記檔案當成資料庫拿來餵，  
這樣子太久沒碰的Code就不用慢慢找慢慢搜了(灑花)。  

為了減少資料庫餵整包的負擔，  
在搜尋要載入的筆記檔案時，感覺可以用#tag去做第一次的資料篩選，    
先把函式寫下來以後實作RAG在Obsidian上的時候再來用。  

# 檔案內容  

裡面包含了兩個python函式，分別對應單tag與多tag的情況  

search_files_with_tag(folder_path, tag)  
search_files_with_tags(folder_path, tags)  

單tag : 回傳檔案名稱表  
多tag : 回傳檔案的dict key為檔案名稱，value為檔案包含標籤

# 討論紀錄

在使用tag的正則表達式時  
左邊邊界\b 會使得#符號沒有被正確涵蓋而找不到檔案  
因此程式中正則表達式rf'{tag}\b'只涵蓋右邊邊界  
