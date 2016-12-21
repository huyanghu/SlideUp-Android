# SlideUp-Android
SlideUp is a small library that allows you to add sweet slide effect to any view.

---

<img src="/art/art1.gif" width="300"> 
<img src="/art/art2.gif" width="300"> 

---
# Usage

To add the SlideUp into your project, follow these three simple steps:

### Step 1:
create any type of layout

```xml
<LinearLayout
  android:id="@+id/slideView"
  android:layout_width="match_parent"
  android:layout_height="match_parent"/>
```

### Step 2:
Find that view in your activity/fragment
```java
View slideView = findViewById(R.id.slideView);
```

### Step 3:
Create a SlideUp object and pass in your view
```java
SlideUp slideUp = new SlideUp(slideView);
```
## Enjoy!
---
# More complicated example

```java
slideView = findViewById(R.id.slideView);
dim = findViewById(R.id.dim);
fab = (FloatingActionButton) findViewById(R.id.fab);

slideUp = new SlideUp(slideView);
slideUp.hideImmediately();

fab.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View view) {
        slideUp.animateIn();
        fab.hide();
    }
});

slideUp.setSlideListener(new SlideUp.SlideListener() {
    @Override
    public void onSlide(float percent) {
        dim.setAlpha(1 - (percent / 100));
    }

    @Override
    public void onVisibilityChanged(int visibility) {
        if (visibility == View.GONE)
        {
            fab.show();
        }
    }
});
```
