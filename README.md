﻿# MaterialProgressView
### 具有 SwipeRefreshLayout 样式的转圈动画。

#### CircleImageView和MaterialProgressDrawable来自于AOSP的support-v4包，精简了用不到的成员变量和方法。

![https://raw.githubusercontent.com/xingda920813/MaterialProgressView/master/video.gif](https://raw.githubusercontent.com/xingda920813/MaterialProgressView/master/video.gif)

#### 支持wrap\_content和LayoutParams.WRAP_CONTENT;

#### 可自定义转圈的颜色和转圈所在圆形突起的背景色 :

```
//设置转圈的颜色为蓝红两色渐变交替
progressView.setColorSchemeColors(new int[]{getResources().getColor(R.color.colorPrimary), getResources().getColor(R.color.colorAccent)});
//设置转圈所在圆形突起的背景色为默认的浅灰色
progressView.setProgressBackgroundColor(Color.parseColor("#FAFAFA"));
```

#### setVisibility具有与ProgressBar相同的行为：setVisibility(int visibility)中参数为View.INVISIBLE或View.GONE时，停止动画并复位状态（圆弧颜色和旋转的程度），参数为View.VISIBLE时，开始动画。

因此可用于RecyclerView.Adapter的ProgressViewHolder，用于加载更多指示器的实现。加载完成后，调用MaterialProgressView.setVisibility(View.INVISIBLE / View.GONE)；开始加载时，调用MaterialProgressView.setVisibility(View.VISIBLE)，因为状态已重置过，所以动画将从头播放、颜色也会取int[]中的第一种颜色，然后每转一圈换一种颜色。

Adapter和ProgressViewHolder示例详见sample.

## 引入

build.gradle中添加

    compile 'com.xdandroid:materialprogressview:+'
