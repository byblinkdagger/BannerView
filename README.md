# a simple BannerView which can auto switch pages based on ViewPager and LinearLayout.

# update 2017-08-24 解决了多此界面返回后轮播混乱的问题 

* dependencies（依赖）

```
compile 'com.coldmoqiuli:banners:1.0.0'
```

* useage（传递进一个List<ImageView>,如需listener,clicklistener也在创建ImageView的时候自行处理好即可）

```
        bannerView = (BannerView) findViewById(R.id.banner);
        bannerView.setViewList(viewList);
        bannerView.startLoop(true);
```

* like this 

<img src="/screen/banners.gif" alt="screenshot" title="screenshot" width="270" height="486" />

