# BottomNavigationViewDemo
BottomNavigationViewDemo

导入包
    implementation 'com.android.support:design:28.0.0'


禁止item水平平移动画效果:
    app:itemHorizontalTranslationEnabled="false"
    对应的的方法是setItemHorizontalTranslationEnabled(false)


设置导航栏的显示模式
    app:labelVisibilityMode="labeled"
    该属性对应的方法是setLabelVisibilityMode(LabelVisibilityMode.LABEL_VISIBILITY_LABELED)
    auto:当item小于等于3是，显示文字，item大于3个默认不显示，选中显示文字
    labeled:始终显示文字
    selected:选中时显示
    unlabeled:始终不显示文字


设置icon选择与未选状态颜色
    app:itemIconTint="@drawable/bottom_navigation_selector"
设置文本选择与未选状态颜色
    app:itemTextColor="@drawable/bottom_navigation_selector"

    bottom_navigation_selector.xml
    <?xml version="1.0" encoding="utf-8"?>
    <selector xmlns:android="http://schemas.android.com/apk/res/android">
        <item android:color="@color/tab_unchecked" android:state_checked="false" />
        <item android:color="@color/tab_checked" android:state_checked="true" />
    </selector>


设置菜单引用
    app:menu="@menu/my_navigation_items"


设置item点击事件监听
    navigation.setOnNavigationItemSelectedListener(this)

    override fun onNavigationItemSelected(p0: MenuItem): Boolean {
        when (p0.itemId) {
            R.id.action_search -> return true
            R.id.action_settings -> return true
            R.id.action_navigation -> return true
            R.id.action_me -> return true
        }
        return false
    }
