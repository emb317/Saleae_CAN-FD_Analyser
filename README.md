# Saleae_CAN-FD_Analyser
A CAN or CAN-FD Analyser to extend the functionality of the Saleae logic analyser product family.

Code built via Visual Studio 2017, tested under Windows 10 x64.

---

Saleaeロジックアナライザー製品ファミリの機能を拡張するCANまたはCAN-FDアナライザー。

Visual Studio 2017を介してビルドされ、Windows 10 x64でテストされたコード。

**CANFD_original.dll** はフォーク元のコードをビルドしたオリジナル。  
**CANFD.dll** は以下の変更を加えたもの。

- 5Mbps/8Mbpsに対応
    - SOFからの一定のサンプリングレートでサンプリングしていたため、高bpsだと後半がずれてしまう。  
エッジで同期するように変更した。  
    - BRSでビットレートが変わった際にサンプリング位置がずれていた。  
ビットレートに合わせてサンプリング位置を変えるように変更した。
- Stuffcountを表示するよう変更
- CAN FDのCRC長 17/21bit を表示するよう変更
- ACKを取りこぼす問題に対応
    - ACKのサンプリングが早すぎたためCRC Delimiterの位置でサンプリングしてしまい、NAKと検知してしまう。  
    サンプリング位置を後ろにずらした。
    
