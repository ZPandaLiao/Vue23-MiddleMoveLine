# Vue23-MiddleMoveLine
同时支持vue2、vue3的中线分割组件，可以实现拖动的效果

和这个组件实现功能一致（但支持vue2/vue3）：[Vue Split Pane](https://github.com/PanJiaChen/vue-split-pane)

![演示图](https://img-blog.csdnimg.cn/69a63c9a78aa40a697dc766a4fd63c69.gif)


# usage|使用方法：

特殊：vue3可能需要安装 scss---> 
```sh
npm install -D sass 
```

1. 将组件代码复制到你的项目组件内即可使用\
不需要获得授权，请尽情div|自定义


---

2. 属性：看源码即可，源码给出详细注释

direction：【字符串】切割方向，\
默认是x表示A、B分割左右两份（A、B排列方向为x横向），可选y---A、B纵向排列

safe-distance：【数组】安全距离，\
有默认值----表示左边留空、右边留空| 上面留空、下面留空，单位为px

percent-a:【字符串】 A视图所占百分比\
有默认值，左边| 上面 view视图所占比例，单位是%

z-index：B视图的层级\
一般不需要使用，默认即可

---

3. 用法示例：

App.vue
```css
<MiddleMoveLine :safe-distance="[50,50]" :percent-a="30">
    <template v-slot:paneA>
      <div style="background-color: #5ee012;width: 100%;height: 100%;font-size: 50px">我是第一个panA</div>
    </template>
    
    <template v-slot:paneB>
    
      <MiddleMoveLine direction="y" :safe-distance="[50,50]" :percent-a="60">
        <template v-slot:paneA>
          <div style="background-color: #000000;width: 100%;height: 100%;font-size: 50px;color: white">我是第二个panA</div>
        </template>
    
        <template v-slot:paneB>
          <div style="background-color: #ffffff;width: 100%;height: 100%;font-size: 50px;">我是第二个panB</div>
    
        </template>
      </MiddleMoveLine>
    </template>
</MiddleMoveLine>
```
