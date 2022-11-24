# payment

# 支付系統

## 支付流程設計

1. 生成業務訂單
1. 躍至使用者支付頁面
1. 選擇支付方式
1. 呼叫統一支付介面
1. 支付驗證
1. 生成支付訂單
1. 通路參數路由設定
1. 連線方通路參數設定獲取及對應通路參數封裝
1. 發起第三方支付請求 (支付公司下單)
1. 同步返回支付結果或預支付資訊
1. 統一支付回應資訊封裝 (根據不同支付方式擴充)
1. 回應使用者支付頁面
1. 根據支付方式拉起支付用戶端完成使用者支付 (用戶端)
1. 透過支付通路用戶端 完成支付
1. 成功支付結果通知
1. 結果返回 (頁面跳躍)
1. 支付訂單狀態更新
1. 連線力非同步支付結果通知
1. 生效使用者權益 (錢包餘額表、交易明細表以及交易訂單表更新)


## 支付系統測試是否能用

### 進行Mockito 單元測試

  >系統開發測試的大致流程 ***開發完成*** → ***UnitTest(單元測試)*** →  ***ntegration Test(整合測試)***→***QA測試***→***發佈上線***  
  >
>
  >開發人員應該充分地進行單元測試,避免過多的問題留到 QA 測試階段,從而影響軟體的疊代升級  
  

**(模擬生成物件→模擬Redis分散式鎖物件→模擬dao層依賴方法執行回傳→執行驗證執行過程)**

* 使用"mvn <option -Dtest='class name'> test" 執行單元測試

**請參考 /src/test裡面的PayServiceImplTest.java註解**

```
cd payment
mvn test
```
  
**Results of the test:**
```
unifiedPay Process finished with exit code 0
```

