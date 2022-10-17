# MyTokenERC20
筆記 在繼承的ERC20中.  

constructor 宣告兩個參數name, symbol, 我們可以提供給constructor宣告自己的token要叫什麼名字.  
_mint, , 是一個internal function只有本人,繼承者可以進行呼叫, 傳入兩個參數, 1. 要mint給誰 2. 要mint幾顆.  

於Remix中編譯, 選Goerli 部署.  
<img width="431" alt="image" src="https://user-images.githubusercontent.com/24216536/196118104-8bf988d1-a0d9-4563-a8fc-cbb99332a8bc.png">
測試網區塊認證後, (Contract 地址: 0x91f341AfC26e4141577E36D249f4F9e25DA1eA70).  
並可以於Etherscan上查看到https://goerli.etherscan.io/address/0x91f341AfC26e4141577E36D249f4F9e25DA1eA70.  

其中看到繼承的ERC20合約Function共有.  
三個Tokne 資訊view function.  
name, symbol, decimals.  
八個功能型Function   
totalSupply, balanceOf, transfer, allowance, approve, transferFrom, increaseAllowance, decreaseAllowance,    
<img width="301" alt="image" src="https://user-images.githubusercontent.com/24216536/196120752-c1328c25-f233-4ea0-b0a5-537e84b3d0cc.png">.  
可看到此處total supply為10000000000000000000 -> 10^19 代表_mint 10顆出來一顆為10^18.  

將自己建立的代幣import進入metamask.  
<img width="405" alt="image" src="https://user-images.githubusercontent.com/24216536/196122380-5ff3dd1e-7c0c-477f-9896-43bc01ffc24d.png">.  

試試看transfer, 轉一塊給Account2.  
<img width="405" alt="image" src="https://user-images.githubusercontent.com/24216536/196123362-be41bc6e-1cdc-4ee4-ab15-53fecc1d6954.png">.  
<img width="293" alt="image" src="https://user-images.githubusercontent.com/24216536/196123436-94cbbad8-5638-48a4-af96-88e609a46298.png">.  
<img width="375" alt="image" src="https://user-images.githubusercontent.com/24216536/196123551-51a43b64-dd3f-4518-8c7d-7ca3e879f76e.png">.  

increaseAllowance, 讓第三個帳號可以替第一個帳號轉帳,給他額度為1 Token.  
<img width="285" alt="image" src="https://user-images.githubusercontent.com/24216536/196124001-be9f5b16-96cc-4b21-9fdd-cf3264135d16.png">.  
完成後選Allowance查看確認委派額度為1!   
<img width="285" alt="image" src="https://user-images.githubusercontent.com/24216536/196124471-47cbb9c9-2091-48af-939e-bf9d92f72fb0.png">.  

transferForm, 就可以使用委派的帳號轉帳給其他人.  
<img width="285" alt="image" src="https://user-images.githubusercontent.com/24216536/196125781-82c4c3ed-e207-42db-94c6-cd7187b46b63.png">.  
可以看到多了1個單位的代幣～～.  
<img width="285" alt="image" src="https://user-images.githubusercontent.com/24216536/196125855-2ea4ca32-b743-439c-9d3d-b8e6708ab35f.png">.  

ERC20的簡單功能記錄到這邊
