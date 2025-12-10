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

# 再主进程相关代码加断点（background.js），点击webstrom上debug按钮
