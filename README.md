# Dev Guide Book @Adview

## Contents

[I. Register and configure SDK-KEY](https://github.com/vinith-cit/AdViewSDK_Android-3.4.1/blob/master/README.md#i-register-and-configure-sdk-key)

[II.About AdViewBidSDK_Android_3.4.4](https://github.com/vinith-cit/AdViewSDK_Android-3.4.1/blob/master/README.md#Ⅱabout-adviewsdk_android-341)

[III. Add SDK](https://github.com/vinith-cit/AdViewSDK_Android-3.4.1/blob/master/README.md#iii-add-sdk)

[IV. AndroidManifest.xml text configuration](https://github.com/vinith-cit/AdViewSDK_Android-3.4.1/blob/master/README.md#iv-androidmanifestxml-text-configuration)

[V. Create banner advertising](https://github.com/vinith-cit/AdViewSDK_Android-3.4.1/blob/master/README.md#vi-create-banner-advertising)

[VI. Create interstitial advertising](https://github.com/vinith-cit/AdViewSDK_Android-3.4.1/blob/master/README.md#vii-create-interstitial-advertising)

[VII. Create opening screen ad](https://github.com/vinith-cit/AdViewSDK_Android-3.4.1/blob/master/README.md#viii-create-opening-screen-ad)

[VIII. Create native advertising ](https://github.com/vinith-cit/AdViewSDK_Android-3.4.1/blob/master/README.md#ix-create-native-advertising)

[IX. Create video advertising](https://github.com/vinith-cit/AdViewSDK_Android-3.4.1/blob/master/README.md#x-create-video-advertising)

[X. Adding Proguard-rules](https://github.com/vinith-cit/AdViewSDK_Android-3.4.1/blob/master/README.md#xi-adding-proguard-rules)


[XI. Contact us](https://github.com/vinith-cit/AdViewSDK_Android-3.4.1/blob/master/README.md#xiii-contact-us)



## I. Register and configure SDK-KEY
1. Visit AdView website [adview.com](http://www.adview.com) and complete the registration process.
2. After Login you will land on "My Products" page by default, select **"Publish App”** .
3. Select **“Android”** follow the prompts to complete the relevant information About the application and click on **"Next"** button at the end where you will be redirected to **“APP management”** page
4. Under "App managemnet" page Click **"Next"** button at the bottom --> you will get the sole SDK key --> click **"Finish"** button at the bottom centre of the page and you will be redirected to the below page 


![Bidding](https://raw.githubusercontent.com/vinith-cit/Images-for-github/master/III.1.png)

5. Now click on "configure" against your application, then you will be redirected to **“APP management”** page → under the Ad format you want to configure (Banner,interstitial,video,open screen and native) open the switch against Auction ads(AdView Ads) .

![Home page](https://raw.githubusercontent.com/vinith-cit/Images-for-github/master/auction%20ads.png)


6.For **video ad or native ad**,Please configure in AdView Dash board .Please click **under review or setting** label ,you will get dialog box.In the dialog box For Auction ads ,please click save button in dialog box and  click **save**   button in bottom of the page .For other platforms ,please configure those custom adNetworks ids .


![video ad1](https://raw.githubusercontent.com/vinith-cit/Images-for-github/master/videos1.png)



![video ad2](https://raw.githubusercontent.com/vinith-cit/Images-for-github/master/videos2.png)




7. (Optional) if you wish to show prompt when you click on the ad - Under app management --> select "Edit" against your app, Switch on "Twice confirmation" button under "Advertising text settings".	



![bidding-2](https://raw.githubusercontent.com/vinith-cit/Images-for-github/master/III.2.png)


**Notes:**

1. In This Github repository we have provided you with Adview Android SDK which gives you the freedom to choose your favourite ad network.

2. Bidding and remnant ads need to complement market information at background, if the status is **"Under review"** you will be receiving test ads. and you will get formal ads only after **"pass reviewed"** by the AdView team. 

3. Ads will be shown of only those ad platforms for which the **switch** is on against them.		

4. Only the "capacity" of those ad platforms for which the switch is on will be valid, the ad newtork with higher proportion will get prior request, for all ad platforms with status as ON, the cumulative should be 100%. Other wise the your priority can't be saved.  

5. For Banner ad, full screen/interstitial, opening screen ,etc, there’s a save button at the bottom of the page. You should click the save button every time you modify a ad format, otherwise the modification is invalid . 

6. **Region optimization:** 
Region optimization function means mobile phone displays the regional configured ads when it’s with in the region, while in foreign country it display foreign configured ads to meet the different demands to the maximum extent. When the region optimization function is closed, it does not distinguish between home and abroad. 

7. In case you wish to show the same ad format more than once (like 2 banner ads) you need to create a new project (My product page --> publish app) with same credentials to get a new SDK key and the integration process remains same, you need not create a new project if the ad formats are different

## Ⅱ.About AdViewBidSDK_Android_3.4.4

1. Clone or download AdViewBidSDK_Android_3.4.4 package to go ahead with the integration process. This package contains all files needed for smooth integration and some of the important fils include **AdViewBIDSample** and **libs**.

**AdViewBIDSample**
AdViewBIDSample project which includes all types of ad format (banner,interstitial,video,native,open screen) sample code with explanation.you can run the application. you can see the **test ads**.

**libs**
It contains all the .jar file SDK needed for ad platform integration. 


## III. Add SDK

1. Clone or download AdViewBidSDK_Android_3.4.4 package here.In the AdViewBidSDK_Android_3.4.4 folder contains libs folder ,it contains the SDK for ad platforms.

2. Please copy and paste **AdViewSDK_Android.jar,google-play-services.jar** into your application lib folder.you'll need to integrate the Google Play Services SDK into your app.This is mandatory; without Google Play Services, the SDK cannot function.


![add SDK](https://raw.githubusercontent.com/vinith-cit/Images-for-github/master/IV.png)						  


## IV. AndroidManifest.xml text configuration

**4.1 Add permission code**

Required permissions should be added (please refer to AndroidManifest file in the **AdViewBIDSample** project).

```
  <!-- AdView SDK mandatory or important permissions -->
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    <uses-permission android:name="android.permission.READ_PHONE_STATE" />
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
   
```

**Note:**

-**INTERNET:** allow to visit network (required)                                                                                         
-**ACCESS_NETWORK_STATE:** allow to visit various status of mobile phone (required)                                                     
-**ACCESS_COARSE_LOCATION**: allow a procedure to visit CellID or WIFI to get the rough position.                                       
-**ACCESS_FINE_LOCATION:** allow a procedure to visit the accurate position (for example, GPS)                                           
-**ACCESS_WIFI_STATE:** allow a procedure to visit WIFI status                                                                           
-**WRITE_EXTERNAL_STORAGE:** allow a procedure to visit outside storage device and can cache ads.                                       
-**READ_EXTERNAL_STORAGE:** allow a procedure to visit outside storage device                                                           


**4.2 Add Activity declaration**

The given code should be added to in AndroidManifest file for AdView, as some platforms need to declare activity to work normal, please refer to **AndroidManifest file** in **AdViewBIDSample** project.  

**Configurations that adview bidding ads should add:**

```
	<service android:name="com.kyview.DownloadService" />
	<activity android:name="com.kyview.AdviewWebView" />
	<activity android:name="com.kyview.AdActivity" />
	<!-- Adiview bidding video -->
	<activity android:name="com.kuaiyou.video.vast.activity.VASTAdActivity" 
	android:hardwareAccelerated="true"
	android:screenOrientation="landscape"/>
	
```


## V. Create banner advertising

**5.1 Add ads through adding code**

Add a banner code to layout file,

```
	<FrameLayout
	      android:id="@+id/banner_layout"
	      android:layout_width="match_parent"
              android:layout_height="wrap_content"
	      android:gravity="center_horizontal" />
```

Add the following code to your activity:


```
	//initiate banner (context, sdkKey, adSize, false)
	AdViewBIDView adViewBIDView = new AdViewBIDView(context,sdkKey, AdViewBIDView.BANNER_SMART, false);

	//display the button of ‘close ad’
	adViewBIDView.setShowCloseBtn(false);

	//ad refresh time(second), if don’t configure, default don’t refresh
	adViewBIDView.setReFreshTime(15)
	
	//Animation for Banner
	adViewBIDView.setOpenAnim(true);


	//callback
	adViewBIDView.setOnAdViewListener(onAdListener);
	
	
	LinearLayout layout = (LinearLayout) findViewById(R.id.banner_layout);

	//Adding Banner Ad in the layout
	if (null != layout)
		layout.addView(adViewBIDView);


```




```	

       // onAdClose Call Back method 
 	@Override
	public void onAdClosedAd(View arg0) {
		Log.i("AdViewBID", "onAdClosedAd");
		if (null != adViewBIDView) {
			ViewGroup rootView = (ViewGroup) findViewById(android.R.id.content);
			for (int i = 0; i < rootView.getChildCount(); i++) {
				if (rootView.getChildAt(i) == adViewBIDView) {
					rootView.removeView(adViewBIDView);
				}
			}
		}
		if (null == layout)
			return;
		layout.removeAllViews();
	}

       
```       


**Banner Size Parameter**

|  Sample Name  | size | value |
| --- | --- | --- |
| BANNER_AUTO_FILL |   Fill by the width of screen |  0  |
| BANNER_480*75 |  480*75 |  2  |
| BANNER_728*90 |  728*90 |  3  |
| BANNER_SMART |  recommended |  5  |



**5.2 Ad Banner events handling**

To receive events from ad, **you should implement an event listener interface OnAdViewListener**.
After you implement this listener you will get the following methods.  

```

	public interface OnAdViewListener {
	
		/**
		 * Use this function when the ad is clicked
		 */
	       void onAdClicked(View var1);


		/**
		 * Use this function when the ad is displayed
		 */
	       void onAdDisplayed(View var1);

		/**
		 * Use this function when the ad is Received
		 */
	       void onAdRecieved(View var1);

		/**
		 * Use this function when the ad is Received Failed
		 */
	       void onAdRecieveFailed(View var1, String var2);    


		/**
		 * Use this function when the ad closed
		 */
	       void onAdClosedAd(View var1);   


		/**
		 * Use this function when the ad closed while refreshing 
		 */
	       void onAdSpreadPrepareClosed();

		/**
		 * Use this function when the ad closed by user
		 */
	       void onAdClosedByUser();

		/**
		 * Use this function when the ad is ready
		 */
	       void onAdNotifyCustomCallback(ViewGroup var1, int var2, int var3);


	}


```

**Note:**
You can refer to the code of **AdBannerBIDSample** in **AdViewBIDSample** Project.


## VI. Create interstitial advertising

**6.1 create interstitial**

**Note:**

Since interstitial ad has a certain life cycle, Please do not wait too long after the request to call showAd method, so as to avoid invalid advertising.

Add the following code to your activity:

```
	//Initiate
	AdInstlBIDView adInstlBIDView = new AdInstlBIDView(context, sdkKey, true);

	//callback 
	adInstlBIDView.setOnAdInstlListener(onAdListener);


		
```
	
	
```	
	//AdReceived CallBack
	@Override
	public void onAdRecieved(View arg0) {
		/**
		 * Showing Interstitial Ad
		 */
		adInstlBIDView.showInstl(this);
	}


```

**6.2 Ad Interstitial Event Handling**

To receive events from ad, **you should implement an event listener interface OnAdViewListener**.
After you implement this listener you will get the following methods.  


```



	public interface OnAdViewListener {
	
		/**
		 * Use this function when the ad is clicked
		 */
	       void onAdClicked(View var1);


		/**
		 * Use this function when the ad is displayed
		 */
	       void onAdDisplayed(View var1);

		/**
		 * Use this function when the ad is Received
		 */
	       void onAdRecieved(View var1);

		/**
		 * Use this function when the ad is Received Failed
		 */
	       void onAdRecieveFailed(View var1, String var2);    


		/**
		 * Use this function when the ad closed
		 */
	       void onAdClosedAd(View var1);   


		/**
		 * Use this function when the ad closed while refreshing 
		 */
	       void onAdSpreadPrepareClosed();

		/**
		 * Use this function when the ad closed by user
		 */
	       void onAdClosedByUser();

		/**
		 * Use this function when the ad is ready
		 */
	       void onAdNotifyCustomCallback(ViewGroup var1, int var2, int var3);


	}

```

**6.3 Create custom style interstitial**

You can customize the popup Intrstitial ad, please refer AdInstlActivity for the entire code .Please refer **AdInstlBIDSample** in **AdViewBIDSample** Project.
```
	
	//Initiate
	AdInstlBIDView adInstlBIDView = new AdInstlBIDView(context, sdkKey, true);

	//callback 
	adInstlBIDView.setOnAdInstlListener(onAdListener);
	
	//OnAdReceived CallBack
	@Override
	public void onAdRecieved(View arg0) {
	
	Log.i("AdViewBID", "onAdRecieved");
	// If you use a custom Interstitial Ad, you can use the following code to get an Interstital ad 

		if (((AdInstlBIDView) arg0).getDialogView() != null) {
			Log.i("AdViewBID", "onReceivedAd");
			((AdInstlBIDView) arg0).reportImpression();
			// adInstlBIDView.showInstl(this);
			int width = ((AdInstlBIDView) arg0).getInstlWidth();
			int height = ((AdInstlBIDView) arg0).getInstlHeight();
			// int width = adInstlMgr.getContentView().;
			// int height = adInstlMgr.getContentView().getHeight();
			View mPopupView = LayoutInflater.from(this).inflate(
					R.layout.exit_popup_window, null);
			RelativeLayout mInstlAdRelativeLayout = (RelativeLayout) mPopupView
					.findViewById(R.id.rl_instl);
			// PopupWindow mPopupWindow = new
			// PopupWindow(mInstlAdRelativeLayout, width, height, true);
			mInstlAdRelativeLayout.addView(adInstlBIDView.getDialogView());
			LinearLayout mExitLL = (LinearLayout) mPopupView
					.findViewById(R.id.ll_left);
			LinearLayout mGoWatchLL = (LinearLayout) mPopupView
					.findViewById(R.id.ll_right);
			// mExitLL.setOnClickListener(mListener);
			// mGoWatchLL.setOnClickListener(mListener);
			mPopupWindow = new PopupWindow(mPopupView,
					RelativeLayout.LayoutParams.MATCH_PARENT,
					RelativeLayout.LayoutParams.MATCH_PARENT, true);

			RelativeLayout.LayoutParams c_params = new RelativeLayout.LayoutParams(
					width, height + dip2px(this, 50));
			c_params.addRule(RelativeLayout.CENTER_IN_PARENT);
			RelativeLayout rl_contentLayout = (RelativeLayout) mPopupView
					.findViewById(R.id.rl_content);
			rl_contentLayout.setLayoutParams(c_params);

			RelativeLayout.LayoutParams b_params = new RelativeLayout.LayoutParams(
					width, dip2px(this, 45));
			b_params.addRule(RelativeLayout.BELOW, R.id.rl_instl);
			RelativeLayout fl_bottom = (RelativeLayout) mPopupView
					.findViewById(R.id.fl_bottom);
			fl_bottom.setLayoutParams(b_params);

			mPopupWindow.setBackgroundDrawable(new BitmapDrawable());
			mPopupWindow.setAnimationStyle(android.R.anim.fade_in);
			mPopupWindow.update();
			mPopupWindow.setTouchable(true);
			mPopupWindow.setOutsideTouchable(true);
			mPopupWindow.setFocusable(true);
			mPopupWindow.showAtLocation((this).getWindow().getDecorView(),
					Gravity.CENTER, 0, 0);

		}
	}

```

**Note:**
Please refer to the code of popup Interstitial ad in **AdInstlBIDSample** in **AdViewBIDSample** Project.

## VII. Create opening screen ad

**7.1 Create opening screen ad**

Add the following code to your activity:

Example We are here used Relative Layout for Opening Screen ad,

```
	<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
	    android:id="@+id/spreadlayout"
	    android:layout_width="match_parent"
	    android:layout_height="match_parent"
	    android:orientation="vertical" >

	</RelativeLayout>

```

Add the following code to your activity:

```
	//Initiate Spread
	AdSpreadBIDView  adSpreadBIDView = new AdSpreadBIDView(this, MainActivity.sdkKey,
				(RelativeLayout) findViewById(R.id.spreadlayout));

	//Config the countdown on the right top, default no
	adViewBIDSpread.setSpreadNotifyType(AdSpreadBIDView.NOTIFY_COUNTER_NULL);

	//Splash screen logo
	adViewBIDSpread.setLogo(logoDrawable);

	// config bg color of ad 
	adViewBIDSpread.getParentLayout().setBackgroundDrawable(backgroundColor);

	//config callback
	adViewBIDSpread.setOnAdSpreadListener(onAdListener);


```


```

	/**
	 * While Displaying Ad
	 * We are Showing counter timer and skip button and in the Ad
	 * @param view
	 * @param ruleTime
	 * @param delayTime
	 */
	@Override
	public void onAdNotifyCustomCallback(final ViewGroup view,
			final int ruleTime, final int delayTime) {
		final TextView tv1 = new TextView(this);
		final Button btn1 = new Button(this);
		final LayoutParams btnLp = new LayoutParams(LayoutParams.WRAP_CONTENT,
				LayoutParams.WRAP_CONTENT);
		final LayoutParams tvLp = new LayoutParams(LayoutParams.WRAP_CONTENT,
				LayoutParams.WRAP_CONTENT);

		tv1.setTextSize(TypedValue.COMPLEX_UNIT_SP, 20);
		btn1.setId(123123);
		btn1.setText("Skip");
		tv1.setText(ruleTime + delayTime + "");

		btnLp.addRule(RelativeLayout.ALIGN_PARENT_RIGHT);
		tvLp.addRule(RelativeLayout.LEFT_OF, btn1.getId());

		view.postDelayed(new Runnable() {

			@Override
			public void run() {
				btn1.setVisibility(View.VISIBLE);
				//Skip Button for Closing Ad
				btn1.setOnClickListener(new OnClickListener() {
					@Override
					public void onClick(View v) {
						adSpreadBIDView.cancelAd();
					}
				});
			}
		}, ruleTime * 1000);
		view.postDelayed(new Runnable() {

			//Counter timer for Text View

			@Override
			public void run() {
				if (ruleTime + delayTime - count >= 1) {
					tv1.setText(ruleTime + delayTime - count + "");
					count++;
					view.postDelayed(this, 1000);
				}
			}
		}, 1000);
		view.addView(btn1, btnLp);
		view.addView(tv1, tvLp);
		btn1.setVisibility(View.INVISIBLE);

	}




```

**7.2 Ad Opening screen Event Handling**

To receive events from ad, **you should implement an event listener interface OnAdViewListener**.
After you implement this listener you will get the following methods.  


```
	public interface OnAdViewListener {
	
		/**
		 * Use this function when the ad is clicked
		 */
	       void onAdClicked(View var1);


		/**
		 * Use this function when the ad is displayed
		 */
	       void onAdDisplayed(View var1);

		/**
		 * Use this function when the ad is Received
		 */
	       void onAdRecieved(View var1);

		/**
		 * Use this function when the ad is Received Failed
		 */
	       void onAdRecieveFailed(View var1, String var2);    


		/**
		 * Use this function when the ad closed
		 */
	       void onAdClosedAd(View var1);   


		/**
		 * Use this function when the ad closed while refreshing 
		 */
	       void onAdSpreadPrepareClosed();

		/**
		 * Use this function when the ad closed by user
		 */
	       void onAdClosedByUser();

		/**
		 * Use this function when the ad is ready
		 */
	       void onAdNotifyCustomCallback(ViewGroup var1, int var2, int var3);


	}


```

**Note:**
Please refer to the code of **SpreadActivity** in **AdViewBIDSample** Project.


**7.3 Custom notification on top of opening screen with countdown options** 

```
	// Skip button will appears on the top after settings
	AdViewSpreadManager.getInstance(this).setSpreadNotifyType(this, AdSpreadManager.NOTIFY_COUNTER_NUM);

	// Defaults, none notification will be displayed
	public final static int NOTIFY_COUNTER_NULL = 0;

	// Countdown will be shown after settings
	public final static int NOTIFY_COUNTER_NUM = 1;

	// Skip button will be shown on the top after settings,but it will appear only after specified times.
	public final static int NOTIFY_COUNTER_TEXT = 2;

	// Will call this after settings:onAdNotifyCustomCallback(String key,ViewGroup view,intruleTime,int delayTime)                 //interface, you can custom notification styles
	public final static int NOTIFY_COUNTER_CUSTOM = 3;

```

**Note:**

For opening advertising please make sure the exposure time is sufficient, otherwise it will affect the ad revenue. 
Please refer to the code of **SpreadActivity** in **AdViewBIDSample** Project.

## VIII. Create native advertising 

**8.1 create native advertising**

Add the following code to your activity:

```
	//initiate
	AdViewNative  adViewNative = new AdViewNative(this, appId, posId, nativeCallBcak);
	
	//request (optional param: ad numbers)
	adViewNative.requestAd();
	
	
```			


```
	/**
	 * onNativeAdReceived CallBack
	 * Once Received Ad ,we are showing in the NAtive item layout
	 * You can get the more than one Ad
	 * even You can use  listview for more than one ad
	 * @param nativeAdList
	 */
	@Override
	public void onNativeAdReceived(List nativeAdList) {
		Log.i("AdViewBID", "onNativeAdReceived");
		if (null != nativeAdList && !nativeAdList.isEmpty()) {
			//Getting only one Ad From nativeAdList
			NativeAdBean nativeBean = (NativeAdBean) nativeAdList.get(0);
			LayoutInflater inflater = LayoutInflater.from(this);

			//Native Ad Item
			final View contentView = inflater.inflate(R.layout.item4, null);
			WebView icon = (WebView) contentView.findViewById(R.id.icon);
			WebView image = (WebView) contentView.findViewById(R.id.image);
			TextView title = (TextView) contentView.findViewById(R.id.title);
			TextView desc = (TextView) contentView.findViewById(R.id.desc);
			TextView desc2 = (TextView) contentView.findViewById(R.id.desc2);
			TextView likes = (TextView) contentView.findViewById(R.id.likes);

			popupWindow.setFocusable(true);
			popupWindow.setBackgroundDrawable(new BitmapDrawable());
			popupWindow.setContentView(contentView);
			popupWindow.setHeight(LinearLayout.LayoutParams.WRAP_CONTENT);
			popupWindow.setWidth(LinearLayout.LayoutParams.MATCH_PARENT);
			popupWindow.showAtLocation(this.getWindow().getDecorView(),
					Gravity.CENTER, 0, 0);

			if (null != nativeBean) {
						
				desc.setText(nativeBean.getDesc());
				desc2.setText(nativeBean.getDesc2());
				title.setText(nativeBean.getTitle());
				likes.setText(nativeBean.getLikes());
				if (!TextUtils.isEmpty(nativeBean.getImageUrl()) && null != image)
					image.loadData(
							(new String(HTML)).replace("image_path", nativeBean.getImageUrl()),
							"text/html; charset=UTF-8", null);

				if (!TextUtils.isEmpty(nativeBean.getIconUrl()) && null != icon)
					icon.loadData(
							(new String(HTML)).replace("image_path", nativeBean.getIconUrl()),
							"text/html; charset=UTF-8", null);

				popupWindow.update();

				// Impression report
				adViewNative
						.reportImpression(nativeBean.getAdId());

				/***************************************************************/
				// Fire ad click report
				if (null != icon)
					icon.setOnTouchListener(new View.OnTouchListener() {
						@Override
						public boolean onTouch(View v, MotionEvent event) {
							if (event.getAction() == MotionEvent.ACTION_UP
									&& (event.getEventTime()
											- event.getDownTime() < 300))
								if (null != contentView)
									contentView.performClick();
							return false;
						}
					});
				if (null != image)
					image.setOnTouchListener(new View.OnTouchListener() {
						@Override
						public boolean onTouch(View v, MotionEvent event) {
							if (event.getAction() == MotionEvent.ACTION_UP
									&& (event.getEventTime()
											- event.getDownTime() < 300))
								if (null != contentView)
									contentView.performClick();
							return false;
						}
					});
				if (null != contentView)
					contentView.setOnClickListener(new View.OnClickListener() {
						@Override
						public void onClick(View v) {
							adViewNative.reportClick(nativeBean.getAdId());
						}
					});
				/***************************************************************/
			}
		}
	}

```
**Note:**

please refer to the code of **AdNativeBIDSample** in **AdViewBIDSample** Project.



**8.2 Ad Native Event Handling**

To receive events from ad, **you should implement an event listener interface NativeAdCallBack**.
After you implement this listener you will get the following methods.  


```
    public interface NativeAdCallBack {

        /**
         * This function is called when the ad request succeed.
         */
        public void onNativeAdReceived(List nativeAdList) {

        /**
         * This function is called when ad request failed.
         */
        public void onNativeAdReceiveFailed(String var1);

        /**
         * When the ad status changed.
         */
        void onDownloadStatusChange(int status);

    }

```

## IX. Create video advertising
**9.1 create video advertising**

Add the following code in activity,

```
	//AdViewVideoManager for AdView Video Ad
	AdViewVideoManager videoManager = new AdViewVideoManager(this, APPID, POSID, this, false);

	// Set the screen orientation，Values can be referenced by ActivityInfo.SCREEN_XXXXXX Defined constants
	videoManager.setVideoOrientation(ActivityInfo.SCREEN_ORIENTATION_LANDSCAPE);
	
```



```
	
	//Once video loaded ,then playing the video
	@Override
	public void onVideoReady() {
		Log.i(TAG, "onVideoReady");
		videoManager.playVideo(this);
	}


```

**9.2 Ad Video Event Handling**

To receive events from ad, **you should implement an event listener interface AdViewVideoListener**.
After you implement this listener you will get the following methods.  


```    
    
    public interface AdViewVideoInterface {
    
        /**
         * Received Event notification
         */    
        void onReceivedVideo(String var1);
	 
        /**
         * Received failed notification
         */
  	void onFailedReceivedVideo(String var1);
	
        /**
         * Video Ready event notification
         */
   	void onVideoReady();
	 
        /**
         * Play start event notification
         */
   	void onVideoStartPlayed();
	 
        /**
         * Video Finish event notification
         */
        void onVideoFinished();

        /**
         * Video Closed event notification
         */
       void onVideoClosed();

        /**
         * Played Error notification notification
         */
 	void onPlayedError(String var1);
	
	}


```

**Note:**

You can refer to the code of **AdVideoBIDSample** in **AdViewBIDSample** Project.


## X. Adding Proguard-rules 

If you have a ProGuard configuration file please add the below lines of code in proguard-rules.pro file

```	
	-dontwarn
	-keep public class com.kyview.** {*;} 
	-keepclassmembers class * {public *;}
	-keep public class  com.kuaiyou.**.** {*;}
	-optimizationpasses 5
	-dontusemixedcaseclassnames
	-dontskipnonpubliclibraryclasses
	-dontpreverify
	-verbose

```






## XI. Contact us 

Users can login Adview, there are service E-mail, service contact number and enterprise QQ customer service at the bottom of the homepage 

![custom ad platform](https://raw.githubusercontent.com/vinith-cit/Images-for-github/master/VII.png)


