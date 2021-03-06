## ImageMap
[![Build Status](https://travis-ci.org/qiuziz/react-image-map.svg?branch=master)](https://travis-ci.org/qiuziz/react-image-map)
![npm](https://img.shields.io/npm/v/@qiuz/react-image-map)
![David](https://img.shields.io/david/dev/qiuziz/react-image-map)

> 一个使用百分比添加热区的`React`组件

### 安装
```sh
$ yarn add @qiuz/react-image-map
# or
$ npm install @qiuz/react-image-map
```

### 获取热区配置

打开 [https://qiuziz.github.io/react-image-map](https://qiuziz.github.io/react-image-map/) 

或者 传递`imgSrc`参数  [https://qiuziz.github.io/react-image-map?imgSrc=img_address](https://qiuziz.github.io/react-image-map?imgSrc=http://5b0988e595225.cdn.sohucs.com/images/20170920/2a178d11bc8b4178a387398b5658e105.jpeg)



![page](https://raw.githubusercontent.com/qiuziz/react-image-map/master/src/assets/images/page.png)

### 使用
```js
import { ImageMap, Area } from '@qiuz/react-image-map';

interface AreaType extends Area {
	href?: string;
}
```

### 示例
[在线示例](https://codesandbox.io/s/silent-bash-c6zwx)
```jsx
const img = 'https://images.app.goo.gl/STr3xKQMbdjLketR7';

const mapArea = [{"left":"0%","top":"6%","height":"12%","width":"33%"}];

const onMapClick = (area: AreaType, index: number) => {
	const tip = `click map${area.href || index + 1}`;
	console.log(tip);
	alert(tip);
}

<ImageMap
	className="usage-map"
	src={img}
	map={mapArea}
	onMapClick={onMapClick}
/>

// in hooks
const ImageMapComponent = React.useMemo(() => <ImageMap className="usage-map" src={img} map={mapArea} onMapClick={onMapClick} />, [mapArea, img]);

return (
	...

	{ImageMapComponent}

	...
)
```
