# style-vw-loader
一个可以将vue标签内样式px转换vw的 webpack loader


### install

```npm
npm install style-vw-loader --save-dev
```

### Use

vue-cli3

```javascript
{
  chainWebpack: (config) => {
      config.module
      .rule('vue')
      .test(/\.vue$/)
      .use('style-vw-loader')
        .loader('style-vw-loader')
    }
}
```

vue-cli2 

```text
{
    test: /\.(vue|jsx?)$/,
    loader: 'style-vw-loader',
    options: {
       
    }
}
```

### Example

```html
from

<h3 style="font-size: 28px;margin-top: 10px" width="500px">Test</h3>
```

To

```html
<h3 width="66.66667vw" style="font-size: 3.73333vw; margin-top: 1.33333vw;">Test</h3>
```

### option
默认配置
```javascript
defaultsProp = {
  unitToConvert: 'px',
  viewportWidth: 750,
  unitPrecision: 5,
  viewportUnit: 'vw',
  fontViewportUnit: 'vw',
  minPixelValue: 1
}
```

### 参与

只支持vue模板的转换，react模板未提供支持。如果你也有转换style的需求、欢迎参与完善该项目。