# webstom-debug-electron
<img width="772" height="431" alt="截屏2025-12-10 09 44 01" src="https://github.com/user-attachments/assets/060ce5e6-69c5-4297-bf0a-cbba3f0385ba" />

参考上图，配置好以后

# 配置vue.config.js
  // vue.config.js
  
module.exports = {

  configureWebpack: {
  
    devtool: 'source-map'
    
  },
  
  pluginOptions: {
  
    electronBuilder: {
    
      mainProcessFile: 'src/background.js',
      
      chainWebpackMainProcess: (config) => {
      
        config.devtool('source-map')
        
      }
      
    }
    
  }
  
}


# 在主进程相关代码加断点（background.js），点击webstrom上debug按钮 （vue3 ts vite ）


对应 [package.json里是：
"dev:inspect": "electron-vite dev --inspect=5858"

再新增一个 Attach to Node.js/Chrome 配置  Host: localhost
Port: 5858
勾选 Reconnect automatically

先运行 dev:inspect
等控制台出现类似 Debugger listening... 后，再启动 Attach to Node.js/Chrome

启动项目：npm run dev:inspect
调试连接：TestDebug Attach
不要：Debug npm run dev:inspect

如果你现在是在 WebStorm 里给 dev:inspect 这个 npm 脚本点了小虫子，改成点普通绿色三角运行。

<img width="1147" height="695" alt="截屏2026-06-30 09 36 08" src="https://github.com/user-attachments/assets/ccc2461e-0fcd-4e4c-8d81-5d92e81fb31d" /><img width="1465" height="297" alt="截屏2026-06-30 09 35 58" src="https://github.com/user-attachments/assets/30b9e027-5e64-4934-9657-d2ce21590e15" />

