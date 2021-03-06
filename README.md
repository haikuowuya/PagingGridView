PagingGridView
==============

PagingGridView has the ability to add more items on it like PagingListView does. Basically is a GridView with the ability to add more items on it when reaches the end of the list.<br>

Instructions - Maven Central
============

1. Add this library in your build.gradle:

```groovy
dependencies {
    compile 'com.github.nicolasjafelle:paginggridview:1.0'
}
```

Instructions 1
============

1. Clone the git repo
2. Import the "PagingGridView" module into your Android-gradle project.
3. Add "PagingGridView" module in your settings.gradle
4. DONE

Instructions 2 
============
1. Add Nicolas Jafelle's Maven repo to your build.gradle: <a href="https://github.com/nicolasjafelle/maven-repo">Instructions</a>
2. add this dependency: 'com.paginggridview:paging-gridview:1.0.BETA'
3. DONE


How to Use it
================

Simple create your PagingAdapter and add it to com.paging.gridview.PagingGridView.<br>
You have to implements the new Pagingable interface and its onLoadMoreItems() method. For example:<br>
``` java
gridView.setHasMoreItems(true);
gridView.setPagingableListener(new PagingGridView.Pagingable() {
	@Override
	public void onLoadMoreItems() {
		if(pager < 3) {
			new CountryAsyncTask(false).execute();
		}else {
			gridView.onFinishLoading(false, null);
		}
	}
});
```

Finally you can use the onFinishLoading(boolean hasMoreItems, List newItems) method to update the list.
``` java
gridView.onFinishLoading(true, newItems);
```
Also remember to use this package in your layout files: 

	<com.paging.gridview.PagingGridView
        	android:id="@+id/paging_grid_view"
        	android:layout_width="match_parent"
        	android:layout_height="match_parent"/>


Developed By
================

* Nicolas Jafelle - <nicolasjafelle@gmail.com>


License
================

    Copyright 2014 Nicolas Jafelle

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
