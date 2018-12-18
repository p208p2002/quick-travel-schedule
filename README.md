# 快速旅遊排程-結合資訊整合與演算法應用
快速進行旅遊排程，著重在演算法與使用體驗。

## 摘要
出去玩的時候總是快樂，但是出去玩的事前準備也很重要，然而並非所有人都願意花時間
在旅遊的事前規劃上，又或是已經有心儀的景點卻苦惱不知道該如何安排剩下的行程，這些都
是要出去玩之前常遇見的情況，有鑒於此我們希望針對上述情況提供一套快捷的旅遊規劃解決 方案。

## Repository
- [Project](https://gitlab.com/p208p2002/quick-travel-schedule)
- [React](https://gitlab.com/p208p2002/quick-travel-schedule-react)
- [React 佈署環境](https://gitlab.com/p208p2002/quick-travel-schedule-react-server)
- [Laravel](https://gitlab.com/johnny1995johnny1995/quick-travel-schedule-laravel)
- [Laravel(備)](https://gitlab.com/p208p2002/quick-travel-schedule-laravel)
- [Electron](https://gitlab.com/p208p2002/quick-travel-electron)

## 目的
讓使用者在不需規劃或少部分規劃下藉由演算法排定旅遊行程

## 使用技術
以RWD網頁呈現
### 前端
- React 15.6 (Javascript library)
- Jquery (Javascript library)
- Bootstrap 4.0 (CSS library)
- bulma (CSS library)
- tabler (CSS library)

### 後端
- Laravel 5.6 (PHP framework)

### 溝通方式
- Web API (Json格式)

## 內容綱要
預計包含兩個部分
- 演算法旅遊排程
- 旅遊資訊蒐集饋系統

## 演算法旅遊排程
### 要知道的資訊
- 詢問旅遊地區
- 詢問旅遊天數
- 是否有預定好的住宿
- 詢問是否有必去點
- 旅遊的起點、終點與時間
- 旅遊預算(不含往返旅遊地區之車費)

### 模式
#### 模式1(由系統推薦地點)
- 詢問要知道的資訊
- 開始推薦地點(三選一之方式)，畫面一側顯示地圖資訊
- 資訊交由伺服端運算
- 回傳結果於前端

#### 模式2(由系統決定地點)
- 詢問要知道的資訊
- 資訊交由伺服端運算
- 回傳結果於前端

## 使用演算法描述
### 模式1演算法
舉合適之三點給使用者選取(推選三個點給使用者)，推薦地點須考量到預算等因素

### 模式2演算法
結合預算、時間、地點(含必去)，起點開始最後到達終點。中止條件timeout或得到最佳解，呈現結果清單

## 旅遊資訊蒐集饋系統
建立資料旅資料蒐集系統，減少時間造成的資訊落差，並依蒐集資料供使用者查詢、評價及演算法參考依據。

### 資訊蒐集內容
- 地區點(食、住、玩)
- 地點預計停留時間
- 地點估計花費
- 該地點評價
