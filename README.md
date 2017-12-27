# a simple BannerView which can auto switch pages based on ViewPager and LinearLayout.


##### update 如果Banner图片为2张，则需要改变一下setViewList的策略(将new ImageView的步骤移至此处，clicklistener也同理)

```
    public void setViewList(List<YourImageBean> viewList) {
        this.viewList = viewList;
        if (viewList != null && viewList.size() != 0) {
            viewSize = viewList.size();
            if (viewSize == 2) {
                viewList.add(viewList.get(0));
                viewList.add(viewList.get(1));
            }
        }
        List<View> imageViews = new ArrayList<>();
        for (int i = 0; i < viewList.size(); i++) {
            ImageView image = new ImageView(getContext());
            image.setLayoutParams(new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MATCH_PARENT, ViewGroup.LayoutParams.MATCH_PARENT));
        //设置显示格式
            image.setScaleType(ImageView.ScaleType.FIT_XY);
            image.setImageResource(viewList.get(i));
            imageViews.add(image);
        }
        BannerAdapter bannerAdapter = new BannerAdapter(imageViews);
        setAdapter(bannerAdapter);
    }
```

##### update 2017-08-24 解决了从其他界面返回后banner轮播混乱的问题

* dependencies（依赖）

```
compile 'com.coldmoqiuli:banners:1.0.1'
```

* useage（传递进一个List<ImageView>,如需listener,clicklistener也在创建ImageView的时候自行处理好即可）

```
        bannerView = (BannerView) findViewById(R.id.banner);
        bannerView.setViewList(viewList);
        bannerView.startLoop(true);
```

* like this 

<img src="/screen/banners.gif" alt="screenshot" title="screenshot" width="270" height="486" />

