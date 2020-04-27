# Golang_redis
## Redis
Redis 是一個 in-memory 的 key-value database，因此常常被用在需要快取（Cache）一些資料的場合，可以減輕許多後端資料庫的壓力。
Redis 好用的地方就在於速度很快，所以若是開發上碰到一些場合需要速度很快的話，你可以先考慮看看 Redis 是不是能夠幫助到你。
EX:
1. 使用者新增短網址，系統亂數產生 abc123 對應到 http://techbridge.cc
2. 把 key=abc123, value=http://techbridge.cc 寫進資料庫
3. 同上，但是是儲存在 Redis
4. 當有使用者點擊：abc123 這個網址時，先去 Redis 查有沒有這個 key
5. 有的話，redirect 到對應的網址
6. 沒有的話，只好去資料庫查，查完之後記得寫一份到 Redis
