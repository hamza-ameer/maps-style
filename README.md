# maps-style




1)

Add the follwoing dependency into your app level gradle file:
   
    implementation 'com.google.android.gms:play-services-maps:16.1.0'


   

------------------------------------------------------------------------------------------------------------

2)

Add the following permission in menifest file:

	<uses-permission android:name="android.permission.INTERNET" />
	

------------------------------------------------------------------------------------------------------------


3) Add the following meta-data inside the application tag in your menifest file and place your api key:

    <meta-data
        android:name="com.google.android.geo.API_KEY"
        android:value="YOUR API KEY" />

 
     Note: Don't use my API KEY as it will not work for you. Watch our previous videos to get your maps API KEY if you don't have!
    
  


------------------------------------------------------------------------------------------------------




4)  Update the following fragment into your activity_main.xml file with:


     <fragment xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/map"
        tools:context=".MainActivity"
        android:name="com.google.android.gms.maps.SupportMapFragment" />



------------------------------------------------------------------------------------------------------

5)  Update Your MainActivity.java file with:
     public class MainActivity extends AppCompatActivity implements OnMapReadyCallback {
    private GoogleMap mMap;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        getSupportActionBar().hide();
        SupportMapFragment mapFragment = (SupportMapFragment) getSupportFragmentManager().findFragmentById(R.id.map);
        mapFragment.getMapAsync(this);
    }

    @Override
    public void onMapReady(GoogleMap googleMap) {
        try {
            boolean success = googleMap.setMapStyle(MapStyleOptions.loadRawResourceStyle(this, R.raw.map_style));
        } catch (Resources.NotFoundException e) {
        }
        mMap = googleMap;
     }
    }




--------------------------------------------------------------------------------------------------------------------------------------


6) Create you custom map style by follwing the link below:

	=>  https://mapstyle.withgoogle.com/



-----------------------------------------------------------------------------------------------------------------------------------------




7) Create a raw directory inside your application resource folder and follow thses steps:

    i) create a file named "map_style.json" (you can change this name).
    ii) Paste your JSON style string into the file 




-----------------------------------------------------------------------------------------------------------------------------------------





8) Test Your App and Enjoy!



