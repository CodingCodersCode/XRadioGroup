[![](https://jitpack.io/v/fodroid/XRadioGroup.svg)](https://jitpack.io/#fodroid/XRadioGroup)

# XRadioGroup
可以实现任意嵌套RadioButton

<img src="https://github.com/fodroid/XRadioGroup/blob/master/capture/device-2017-02-10-161156.png" width="480" height="800"></img>

# 更新
### v1.5
* 解决依赖的库冲突问题

#Usage 使用

`gradle`

Add it in your root build.gradle at the end of repositories:

    allprojects {
	    repositories {
		        ...
		        maven { url 'https://jitpack.io' }
	    }
    }
Add the dependency

	dependencies {
	        compile 'com.github.fodroid:XRadioGroup:v1.1'
	}

`maven`

	<repositories>
		<repository>
		    <id>jitpack.io</id>
		    <url>https://jitpack.io</url>
		</repository>
	</repositories>

	<dependency>
	    <groupId>com.github.fodroid</groupId>
	    <artifactId>XRadioGroup</artifactId>
	    <version>v1.1</version>
	</dependency>



java代码中使用方式与`android.widget.RadioGroup`完全一致
```java
        XRadioGroup xRadioGroup = (XRadioGroup) findViewById(R.id.xRadioGroup);
        xRadioGroup.setOnCheckedChangeListener(new XRadioGroup.OnCheckedChangeListener() {
             @Override
             public void onCheckedChanged(XRadioGroup group, @IdRes int checkedId) {
                  Log.d("TAG", checkedId + "is checked");
             }
         });
```
在xml中你可以里面嵌套使用
```java
        <me.shihao.library.XRadioGroup
                android:id="@+id/xRadioGroup"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="vertical">

                <RelativeLayout
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:layout_centerHorizontal="true"
                    android:layout_centerVertical="true">

                    <RadioButton
                        android:id="@+id/radioButton"
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_alignParentLeft="true"
                        android:layout_alignParentStart="true"
                        android:layout_alignParentTop="true"
                        android:checked="true"
                        android:text="New RadioButton"/>

                    <RadioButton
                        android:id="@+id/radioButton2"
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_alignParentEnd="true"
                        android:layout_alignParentRight="true"
                        android:layout_alignParentTop="true"
                        android:layout_gravity="center_horizontal"
                        android:text="New RadioButton"/>

                    <RadioButton
                        android:id="@+id/radioButton3"
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_alignParentLeft="true"
                        android:layout_alignParentStart="true"
                        android:layout_below="@+id/radioButton"
                        android:layout_gravity="center_horizontal"
                        android:text="New RadioButton"/>

                    <RadioButton
                        android:id="@+id/radioButton4"
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_alignParentEnd="true"
                        android:layout_alignParentRight="true"
                        android:layout_alignTop="@+id/radioButton3"
                        android:text="New RadioButton"/>

                    <RadioButton
                        android:id="@+id/radioButton5"
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_below="@+id/radioButton3"
                        android:layout_centerHorizontal="true"
                        android:text="New RadioButton"/>

                    <RadioButton
                        android:id="@+id/radioButton6"
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_alignLeft="@+id/radioButton5"
                        android:layout_alignStart="@+id/radioButton5"
                        android:layout_below="@+id/radioButton5"
                        android:text="New RadioButton"/>
                </RelativeLayout>
            </me.shihao.library.XRadioGroup>
```

## 相关文章

[如何使RadioGroup支持RadioButton任意嵌套](http://www.jianshu.com/p/b2ad0140ee8a)

#### 如果你觉得有用，请不吝star
