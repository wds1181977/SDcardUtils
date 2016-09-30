# SDcardUtils

 Android有的手机把手机存储默认改为内部存储设备，造成Environment.getExternalStorageDirectory()获取的是内部存储（16G,32G）
 那么怎么获取外置SD卡呢
 获取T卡的需要通过反射StorageManager判断存储介质，通过判断是否可移除是否已经挂载来确定是外置T卡，应用开发现在流行的是用开源工具类# StorageUtils来实  现具体为

ArrayList<StorageBean> storageDatas = StorageUtils.getStorageData(this);//获取所有存储介质
//遍历storageDatas，得到StorageBean

//是否可移除，是则是外置存储，USB或SD卡
storageData.getRemovable();

//是否已挂载
storageData.getMounted().equalsIgnoreCase("mounted");

//获取此存储介质的真实路径
storageData.getPath();



