# BOSS_ZhiPin

## 关于 BOSS 直聘（2026 新版）防爬相关的前端/接口观察记录

---

### 一、打开开发人员工具的方式

1. 先打开**其他网站**，按 `F12` 或 `Shift + Ctrl + I` 打开开发者工具，再把**已登录并打开**的 BOSS 直聘页面地址粘贴到同一浏览器窗口并访问。

   ![image](https://github.com/user-attachments/assets/4f7f80b8-e9cb-43e5-bdab-fa3868895fd2)

   ![image](https://github.com/user-attachments/assets/73f30798-d556-4e42-a4c7-bc3f82c03e39)

   ![image](https://github.com/user-attachments/assets/fb3e873b-485b-45ca-bff9-6a6ebc234a94)

2. 点击**刷新**后，即可在「网络」面板里查看请求的 **负载（Payload）** 等信息。

   ![image](https://github.com/user-attachments/assets/95b59acf-e4ba-43df-9bc2-730288a0a0ce)

   其中可以看到 `joblist.json?_=...` 一类请求；其负载与**侧边栏列表随滚动刷新**的职位数据相关（`?_=` 多为防缓存用时间戳，与业务字段无强绑定）。

---

### 二、列表滚动与单条详情

1. **列表增量**：每滚动一次大约会多加载 **15** 条职位。

   ![image](https://github.com/user-attachments/assets/20967363-734f-43fb-9d85-f27362f7b17f)

2. **详情接口**：列表字段若不足以拼装详情页，可对照网络面板中的  
   `https://www.zhipin.com/wapi/zpgeek/job/detail.json`  
   与列表项中的 `securityId` 等字段的对应关系（具体是否仅依赖 `securityId`，以当时抓包为准）。

3. **参数示例**（`lid` 与序号、时间戳等以实际请求为准）：

   ```text
   &lid=4RMd4t2pCwV.search.1&_=1774707166887
   &lid=4RMd4t2pCwV.search.2&_=1774709590350
