# dialog

## 基于vue dialog组件


主要配合[pcadmin](https://github.com/ksc-fx/pcadmin)使用。
使用方法：
```
npm install pcadmin-dialog
```

```javascript

import button from 'pcadmin-dialog';

```

### Data
| 参数      | 说明          | 类型      | 是否必选                           | 可选值  | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |-------- |
| title |  dialog标题 | String | - | 否 | 标题 |
| isShow | dialog是否显示 | Boolean | - | false | false |


### Events
| 事件名称 | 说明 | 回调参数 |
|---------- |-------- |---------- |
| close | 关闭回调事件 | — |
