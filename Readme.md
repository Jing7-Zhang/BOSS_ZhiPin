# BOSS_ZhiPin
## 关于BOSS直聘26年新版防爬的破解尝试记录

---

### 打开开发人员工具的方式
1. 先开别的网站按 `F12` 或 `Shift+Ctrl+i` ，再将**已登录并打开**的BOSS直聘网址复制过去
     <img width="1860" height="975" alt="image" src="https://github.com/user-attachments/assets/4f7f80b8-e9cb-43e5-bdab-fa3868895fd2" />
     <br />
     <img width="1860" height="970" alt="image" src="https://github.com/user-attachments/assets/73f30798-d556-4e42-a4c7-bc3f82c03e39" />
     <br/>
     <img width="1860" height="960" alt="image" src="https://github.com/user-attachments/assets/fb3e873b-485b-45ca-bff9-6a6ebc234a94" />

     ---
2. 点击**刷新**后就可以获得“负载”信息了
   <img width="1915" height="915" alt="image" src="https://github.com/user-attachments/assets/95b59acf-e4ba-43df-9bc2-730288a0a0ce" />
   <br/>
   这里我们可以看见 `joblist.json?_=1774707166498` 这个文件里的负载装着侧边栏**滚动刷新**的职位信息

   ---

3. 发现每滚动一次就是15个职位更新
   <img width="1860" height="915" alt="image" src="https://github.com/user-attachments/assets/20967363-734f-43fb-9d85-f27362f7b17f" />
   但是我们发现这个信息不全，还是要拿到详情，于是找到 `https://www.zhipin.com/wapi/zpgeek/job/detail.json` 发现后面的url不就是 `joblist.json?_=1774707166498` 里面的 `securityId`么？后面的参数是固定的，再加上数字（第几个职位，从1计数）和时间戳就好了。
   【eg：&lid=4RMd4t2pCwV.search.1&_=1774707166887
          &lid=4RMd4t2pCwV.search.2&_=1774709590350 】
   <img width="1860" height="915" alt="image" src="https://github.com/user-attachments/assets/1ce95f17-ac76-4698-9ca0-cc6a73246c06" />







