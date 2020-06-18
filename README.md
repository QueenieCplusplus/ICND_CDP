# ICND CDP
使用 Cisco Discovery Protocol 管理網路環境。（目前逐步被 LLDP 取代）

原理：藉由傳送多目的地資料框 Multicast 發現其它網路設備。

功能：
即便第三層通訊協定不同，也能使用作用於第二層通訊協定的 CDP 發現同廠的網路設備。

(1) 建立網路架構圖。

(2) 使用設定檔。

(3) 使用映像檔。

使用映像檔案可以從 tftp 上下載，也可從 http 下載。

# no run 

cisco 網路設備預設 cdp enable
如欲關閉則：

    (config)#no cdp run

如欲關閉某介面的 cdp 可節省頻寬

    (config)#sh int  <介面編號>

    (config-if)#no cdp enable 

重啟介面的 cdp 

    (config-if)#cdp enable

# sh cdp neighbors

更細部資訊

    #show cdp neighbors detail

效果等同於 

    #show cdp entry *
    
* 輸出

- [x] 設備識別名稱（臨時名稱）

- [x] IP 位址 (第三層通訊協定)

- [x] 設備平台(platform)

- [x] 設備角色(capability)

- [x] 介面：近端介面(local int)與本設備相連出去(outgoing)的埠(又稱遠端介面 port id)
    
# sh cdp interface

查看此設備的所有介面的設定與狀態。

* 輸出

cdp 封包發送頻率、封裝方式(encapsulation)與保留時間(holdtime)。


# sh cdp traffic

查看此設備每個介面的資料(frame)流量。

* 輸出

cdp 封包收發總數與錯誤次數。
