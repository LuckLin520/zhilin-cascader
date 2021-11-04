#### 使用方法
1､在 script 中引用组件
```javascript
	//此插件已发布到npm，你也可以使用npm i zhilin-cascader来安装到项目 import ZhilinCascader from 'zhilin-cascader'
    const options = [
        {
            value: 'zhejiang',
            label: 'Zhejiang',
            children: [{
                value: 'hangzhou',
                label: 'Hangzhou',
                children: [{
                    value: 'xihu',
                    label: 'West Lake',
                }]
            }]
        },
        {
            value: 'jiangsu',
            label: 'Jiangsu',
            children: [{
                value: 'nanjing',
                label: 'Nanjing',
                children: [{
                    value: 'zhonghuamen',
                    label: 'Zhong Hua Men',
                }]
            }]
        }
    ]
    export default {
        data() {
            return {
                options,
                show: true
            }
        },
        methods: {
            onConfirm(value) {
                console.log(value)
            }
        }
    }
```
2､在 template 中使用组件
```html
<zhilin-cascader
        v-model="show"
        :options="options"
        @confirm="onConfirm"
>
</zhilin-cascader>
``` 
#### 属性说明
| 属性名       | 类型              | 必填 | 默认值   | 说明                                                     |
| ------------ | ----------------- | ---- | -------- | :------------------------------------------------------- |
| v-model      | Boolean           | 是   |          | 控制选择器弹出/隐藏                                      |
| options      | Array/ObjectArray | 是   |          | 格式：[{label:"四川",value:"sc",children:[]}] |
| title        | String            | 否   | "请选择" | 选择器的标题              |
| isFullValue | Boolean          | 否   |   false    | 是否限制选择完每一项才能confirm |
| fieldNames | Object          | 否   | {label:'label',value:'value',children:'children'} |  自定义options中label value children的字段 |
| height        | String            | 否   | 根据设备自适应 | 需要带上相应单位            |
#### 事件说明
| 事件名  | 说明                 | 返回值                                                  |
| ------- | -------------------- | ------------------------------------------------------- |
| change  | 选中项发生改变时触发 | 接收当前选中项value，数组 |
| confirm | 点击确定时触发       | 接收当前选中项value，数组 |

