*** 轉輪式隨機密碼產生器 ***

　這是用 BASH 腳本語言寫的獨立、可閱讀及單一檔案可攜式真隨機密碼產生器。這裡的「獨立」指的是它避免使用任何的外部命令，以減少安全漏洞。你可以用它來產生適合各種場合的密碼，例如電腦登入、銀行提款卡、無線 Wifi 安全等等。

　為何不用Ｃ語言來做這個？首先，Ｃ程式需要編譯，所以對一般使用者而言可攜性沒那麼高。現在我們在很多電腦系統上都有 BASH 可用，使用者只需要複製這個檔案甚至是文字內容，就可以執行了。第二，腳本語言的執行碼實際上就是源碼，而且可以讓人閱讀。使用者可以覆驗，不用再懷疑可執行碼是不是和原始碼相符。這對與安全相關的程式是一個優勢。在這裡惡意軟體只可能是可以認得本程式的直譯器或是系統。最後，就互動式程式而言，Ｃ語言的高效能不是首要考量。

　密碼字元的產生是用類似旋轉輪盤的方式，並且在按下 [Enter] 按鍵時瞬間暫停輪盤。這能使密碼難以預測。密碼的長度、使用哪些候選符號都能經由參數設定。

　在「Auto」模式當中，產生器並不會去『轉輪盤』，而是用 /dev/random 當作隨機來源。在某些作業系統中，這樣會使密碼變得可以預測。使用這個模式可能不是好主意。不過，這個模式讓這個腳本可以被其他的腳本或程式當作密碼來源。其他的程式可以由此取得一份密碼，用來當作拋棄式密碼或是用在自動化作業當中。

　基於安全理由，還有一個迷你版叫作「gnpas」。使用者可以很容易而且快速的閱讀它、編修裡面的設定，然後以 ./gnpas 命令執行。迷你版只用一個命令參數：密碼長度。

　使用本程式時先準備好，接著執行本程式並取得密碼。＊不要＊為了不重要的理由，就重新再取一次密碼。過度篩選密碼會使得密碼變得可以預測。例如，如果每十個密碼裡，有九個因為太難記住而廢棄，那麼所有可能的密碼組合中，只有十分之一可能真正使用。瞭解這一點的攻擊者，在猜密碼的時候速度可以加快為十倍。

　－－好記的密碼不好用，好用的密碼不好記－－

SYNOPSIS(總覽)

        ./genpass [-a] [-c|-n] [密碼長度] [l][u][n][s] [-s ...]
        ./gnpas [密碼長度]

ARGUMENTS(參數)

        l   小寫字母
        u   大寫字母
        n   數字
        s   其他符號

        -e
          簡易模式，使用 'lsunln' 作為候選符號的組合方式

        -a
          自動產生密碼，以 /dev/random 作為隨機來源（不建議使用！）

        -c
          使用各種色彩顯示密碼

        -n
          不使用色彩顯示密碼

        -s
          將接下來的字串作為候選符號

