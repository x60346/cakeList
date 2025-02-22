網站使用 Vue3 搭建。

使用語言：HTML5、CSS3、TypeScript。

-----------------------------------

初始畫面有 5 個：首頁、關於我們、產品列表、產品細項、登入／註冊。

登入後額外開放 3 個：購物車、優惠券、我的最愛。

-----------------------------------

＞ 資料夾內容：

　　@/src/assets：reset.css、所有圖片
  
　　@/src/router：路由規則文件
  
　　@/src/views：路由元件
  
　　@/src/components：共用元件
  
　　@/src/store：pinia管理資料

-----------------------------------

＞ 帳號管理：

　　local storage：儲存登入帳號金鑰
  
　　vue-router：路由守衛，阻擋無金鑰的使用者（未登入）
  
-----------------------------------


＞ 網頁布局（路由交互）

    APP
    ｜－頂部
    ｜   ｜ 
    ｜   ｜ －網頁名稱（點擊返回首頁）
    ｜   ｜ 
    ｜   ｜ －操作列表
    ｜          ｜
    ｜          ｜－首頁（to：@/views/Home.vue）
    ｜          ｜
    ｜          ｜－關於我們（to：@/views/About.vue）
    ｜          ｜
    ｜          ｜－產品列表（to：@/views/Goods.vue）
    ｜          ｜
    ｜          ｜－用戶選單（路由守衛－需token（localStorage紀錄））
    ｜                ｜
    ｜                ｜－購物車（to：@/views/ShoppingCart.vue）
    ｜                ｜
    ｜                ｜－優惠券（to：@/views/Coupon.vue）
    ｜                ｜
    ｜                ｜－我的最愛（to：@/views/Like.vue）
    ｜                ｜
    ｜                ｜－登入／註冊／登出（Login.vue／Register.vue）
    ｜   
    ｜－routerView 區（以路由切換 "@/router/index.ts"）
    ｜
    ｜－底部
    ｜   ｜
    ｜   ｜－聯絡我們
    ｜   ｜
    ｜   ｜－說明文字
    ｜
    ｜－右下操作按鈕
         ｜
         ｜－購物車（to：@/views/ShoppingCart.vue）
         ｜
         ｜－回到頂部


＞ 共用元件

    ｜－優惠券卡片（@/components/CouponItem.vue）
    ｜
    ｜－商品卡片（@/components/GoodsCard.vue）
    ｜
    ｜－列表用input框（@/components/FormInput.vue）
    ｜
    ｜－內容版型（@/components/InfoContent.vue）
    ｜
    ｜－確認跳窗（@/components/Modal.vue）
    ｜
    ｜－提示消息（@/components/Toast.vue）


＞ 資料儲存（使用pinia）

    ｜
    ｜－商品資料（@/stores/goods.ts）
    ｜   ｜
    ｜   ｜－資料類型
    ｜   ｜   ｜
    ｜   ｜   ｜－全商品清單
    ｜   ｜   ｜
    ｜   ｜   ｜－商品類別清單
    ｜   ｜   ｜
    ｜   ｜   ｜－我的最愛清單
    ｜   ｜
    ｜   ｜－方法
    ｜        ｜
    ｜        ｜－隨機推薦
    ｜        ｜
    ｜        ｜－加入／移除我的最愛
    ｜        ｜
    ｜        ｜－加入／移除購物車
    ｜        
    ｜－優惠券（@/stores/coupons.ts）
    ｜  ｜
    ｜  ｜－資料類型
    ｜      ｜
    ｜      ｜－全優惠券清單
    ｜
    ｜－用戶資料（@/stores/memberData.ts）
       ｜
       ｜
       ｜－資料類型
       ｜   ｜
       ｜   ｜－全優惠券清單
       ｜
       ｜－方法
            ｜
            ｜－更動購物車／我的最愛／優惠券
            ｜
            ｜－新增用戶
