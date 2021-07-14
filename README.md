# OPTEE MY CA&TA

### Report

#### 如何產生?
* 在optee目錄下有多個子目錄包括optee_example、optee_client等等，當執行optee/build內的make檔時，這邊的make檔會將c code編譯成binary可執行檔
* 在optee/build/package/"project_name"/下的make file會將TA載入TEE中
* 在optee/build/common.mk 則是設定有關CA binary 被載入到rootfs中的設定
    * 推薦直接複製整個目錄後再修改就好
    * [Issue](https://github.com/OP-TEE/optee_os/issues/3042)

#### 取得時間
* 在CA與TA建立完溝通後，傳送指令給TA，TA判斷指令該執行哪個func，並回傳是否成功
* 時間的部分，因為TEE_TIME含有seconds與millis，所以當CA傳送指令給TA時，需傳入兩個變數，再由TA將變數賦值後，CA就能取得時間值了

### Additional files 
* [Package](https://github.com/kipper0508/optee_get_time_package)

### Screenshot
* [Result](https://imgur.com/a/AzaNITF)
