# jyutsp - 基於rime的粵語雙拼方案

* 基於「jyut6ping3」聲調粵拼詞庫、重要參考「soengping」的設計和自然碼雙拼的佈局的粵語雙拼輸入方案。<br>
* 附帶兩種方案，適合在PC端及mobile端使用，反查設計不同。兩鍵內輸入，附加編碼「；」可以實現精準摘選重碼韻母。<br>
* 採用1993年[香港語言學學會粵語拼音方案](https://www.lshk.org/jyutping)<br>
* [「jyut6ping3」項目主頁](https://github.com/rime/rime-cantonese)<br>
* [「soengping」項目主頁](https://github.com/Over-There-Is/rime-soengping/)<br>
* 感謝以上方案的開發者和維護者。<br>
* [「jyutsp」本項目主頁](https://github.com/MrCorn0-0/jyutsp) by *Mr.Corn* <br>

# 輸入編碼
## 碼表

[![zhihu]](https://www.zhihu.com/question/54691506/answer/1022245649)

[zhihu]:https://pic2.zhimg.com/80/v2-c7ea6ffcfe550d4bc31ef38a27e5edfd_720w.jpg "碼表"

## 聲母
* 大部分輔音都在原有的QWERTY鍵盤位置。採用27鍵盤。忽略聲調。
* kw，gw 分別放在 Q和X 鍵位，E 作為零聲母起始鍵搭配元音。參考 [Over-There-Is](https://github.com/Over-There-Is/rime-soengping/) 的處理，對於 u, ut, ui, un, uk 五個音的聲母不用 k w 換用 q x，減少重碼。 （兼容 ku 的輸入）
* U, I, J 分別是 sh, ch（參考自然碼）和 zh，用法大致同 s, c, z 現代粵語有舌葉音和所謂平舌音的發音區別存在，但在同一個音位，可以混拼。本方案排除 u+i 這一組齊齒呼(只能用s+i)之外，兼容 i/c, j/z 兩種拼法。
* 本方案[j]聲母放在Y鍵。

## 韻母
* 本方案基於[「jyut6ping3」](https://github.com/rime/rime-cantonese)項目的詞典，統計得出最佳韻母分佈，大概82%的字是兩鍵精準編碼。[詳情可見](https://www.zhihu.com/question/54691506/answer/1022245649)。
* 合併eu/iu, em/im.
* 成音節[m], [ng] 直接用 MM，RR 輸入。
* yu韻母放在Y鍵。關於jyu韻，本方案處理為 yu。
* ou放在u的位置，不存在聲母衝突。eoi/ui，yun/un, 同理。（注意 q和x 做u/ui/un/uk的聲母）
* E為零聲母，同時也是e和on（會有部分重碼但少量）。
* T是本方案集4個音的鍵，包括eo/oe(互補), oeng, ut，其中僅有oe和oeng的極其少量的重碼。
* 其餘韻母都會有重碼現象，輸入兩鍵可以得到多個音的結果（大多數情況已經可以得到想要的結果）。
* 通過添加附加區分編碼[;]鍵可以精確到重碼韻母（碼表中用**空格+逗號**隔開）。<br>
e.g. {DQ=[diu]/[deu]+[dak], DQ;=[dak]}, <br>
{SK=[sik]+[sek]/[soek], SK;=[sek]/[soek]}, <br>
{HH=[haam], HH;=HH[haak]}.

# 其他
本方案依賴於
  - [粵語拼音方案jyut6ping3](https://github.com/rime/rime-cantonese)  **`cantonese`**
  - 搜狗雙拼（自然碼修改）  **`double_pinyin_sg`**


iRime環境下的安裝
  1. 根目錄導入jyutsp_mobile.schema.yaml和jyut6ping3.schema.yaml。（若需要雙拼反查則附加double_pinyin_sg.schema.yaml及相應build文件）
  2. build文件夾裡導入jyut6ping3的四個文件（prism, scheme, table<-超過大小限制未上傳, reverse），以及jyutsp_mobile.prism.bin、jyutsp_mobile.schema.yaml、jyutsp_nospaces.reverse.bin。
  3. 配置default.custom.yaml，佈署方案。


反查
  - PC版用「\`」鍵打開，mobile版用「~」鍵打開。默認是搜狗雙拼（自然碼修改）反查。
  - 「Q:」打開用[粵語拼音方案jyut6ping3](https://github.com/rime/rime-cantonese)輸入，「X:」打開用筆畫輸入。


示例

    這是一個示例。/zesiycgosill
    希望大家可以enjoy粵語雙拼方案。/hzmwdvgahoyi enjoy ydyuutp;fwee。
