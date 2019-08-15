# 小程序组件 navigation-bar

小程序自定义导航栏适配 完美解决内容上下不居中 左右不居中 高度不合适的问题

## Navigation

Navigation 是小程序的顶部导航组件，当页面配置 navigationStyle 设置为 custom 的时候可以使用此组件替代原生导航栏

## 使用

- 下载项目代码

```bash
git clone https://github.com/lingxiaoyi/Taro-navigation-bar.git
```

- 进入目录安装依赖，国内用户推荐使用 cnpm 进行加速

```bash
npm i
```

或者

```bash
yarn  i
```

- 启动本地服务器

```bash
npm run dev:weapp # 微信小程序
npm run dev:qq # qq小程序
```

- 用开发者工具打开代码目录,记得把appid改成自己的,或者点击测试号,如果不改就默认是作者的,以防万一不能访问.
- 如遇到自己修改代码或者添加新页面之后,修改了已知的问题后,工具中页面样式还是错乱的话,建议重启服务和开发工具.

## 项目中使用

在代码中 import 需要的组件并按照文档说明使用

```bash
import NavBar from 'taro-navigationbar';
```

## 示例代码

```bash
<!--WXML示例代码-->
<NavBar
          title='有返回和home'
          background='#fff'
          back
          home
          searchBar={false}
          onBack={this.handlerGobackClick}
          onHome={this.handlerGohomeClick}
        />
```

更多使用方式请移步[仓库地址](https://github.com/lingxiaoyi/Taro-navigation-bar)查看demo和使用方式.

## 属性列表

| 属性       | 类型         | 默认值   | 必填 | 说明                                                                                            |
| ---------- | ------------ | -------- | ---- | ----------------------------------------------------------------------------------------------- |
| ext-class  | string       |          | 否   | 添加在组件内部结构的 class，可用于修改组件内部的样式                                            |
| title      | string       |          | 否   | 导航标题，如果不提供，则名为 renderCenter 的 slot 有效                                          |
| background | string       | #ffffff  | 否   | 导航背景色                                                                                      |
| color      | string       | #000000  | 否   | 导航字体颜色                                                                                    |
| iconTheme  | string       | black    | 否   | 主题图标和字体颜色,当背景色为深色时,可以设置'white'                                             |
| back       | boolean      | false    | 否   | 是否显示返回按钮，默认点击按钮会执行 navigateBack，如果为 false，则名为 renderLeft 的 slot 有效 |
| home       | boolean      | false    | 否   | 是否显示 home 按钮，执行方法自定义,或者看例子                                                   |
| searchBar  | boolean      | false    | 否   | 是否显示搜索框，默认点击按钮会执行 onSearch，如果为 false，则名为 renderCenter 的 slot 有效     |
| searchText | string       | 点我搜索 | 否   | 搜索框文字                                                                                      |
| onHome     | eventhandler |          | 否   | 在 home 为 true 时，点击 home 按钮触发此事件                                                    |
| onBack     | venthandler  |          | 否   | 在 back 为 true 时，点击 back 按钮触发此事件，detail 包含 delta                                 |
| onSearch   | eventhandler |          | 否   | 在 searchBar 为 true 时，点击 search 按钮触发此事件                                             |

## Slot

| 名称         | 描述                                                                  |
| ------------ | --------------------------------------------------------------------- |
| renderLeft   | 左侧 slot，在 back 按钮位置显示，当 back 为 false 的时候有效          |
| renderCenter | 标题 slot，在标题位置显示，当 searchBar 为 false title 为空的时候有效 |
| renderRight  | 在导航的右侧显示                                                      |

## 注意

- iconTheme 设置为 white 的时候,一定要记得自己去 json 文件设置"navigationBarTextStyle": "white"
- 跳转搜索页面,在 Android 机子会出现文字被键盘弹起顶出 input 框,解决方案页面设置一个死的高度不要高于 windowHeight - navheight 例子中是设置 500px
- input 框文字抖动问题我是借鉴别人写的,可以最大限度减小文字抖动的大小,提升用户体验
- title searchBar renderCenter 如果全部有内容,是这样的先后显示顺序.
- 默认配置满足不了功能的,请使用 slot 功能,见例子 6 7[仓库地址](https://github.com/lingxiaoyi/Taro-navigation-bar)
- 由于本人精力有限,只测试了常规的 20 多款手机.如有哪种机型出现问题,请备注机型,小程序版本库提问题.本人会以最快方式解决问题.
- 有什么 bug 和建议,还有功能上的问题请提 pr
- 用法和测试 demo 请 clone 代码[仓库地址](https://github.com/lingxiaoyi/Taro-navigation-bar)

## 后续

- 添加其他需要的功能,规划中

## 备注

- 为什么我没添加滚动渐变的例子,因为用JS实现滚动渐变,在我的Android千元测试机上,效果不能直视,故取消.如有需要可以添加样式实现滚动渐变.
- 为什么不支持navbar不固定定位,随页面滚动的功能.因为我观察了市场上99%的小程序,都是固定navbar,故不尝试开发此功能,如果需求很大.可以考虑最近版本开发.
~
创作不易,如果对你有帮助，请给个星星 star✨✨ 谢谢
~
