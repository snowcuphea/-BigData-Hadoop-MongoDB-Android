나의 현재 위치를 지도에 표시하기 



* LocationMapExam.java

```java
package multi.android.map_location_pro.location;

import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;
import androidx.fragment.app.FragmentManager;

import android.Manifest;
import android.content.pm.PackageManager;
import android.location.Location;
import android.location.LocationListener;
import android.location.LocationManager;
import android.os.Build;
import android.os.Bundle;
import android.util.Log;

import com.google.android.gms.maps.CameraUpdate;
import com.google.android.gms.maps.CameraUpdateFactory;
import com.google.android.gms.maps.GoogleMap;
import com.google.android.gms.maps.OnMapReadyCallback;
import com.google.android.gms.maps.SupportMapFragment;
import com.google.android.gms.maps.model.LatLng;
import com.google.android.gms.maps.model.PolylineOptions;

import multi.android.map_location_pro.R;

public class LocationMapExam extends AppCompatActivity implements OnMapReadyCallback {
    String[] permission_list={
            Manifest.permission.ACCESS_COARSE_LOCATION,
            Manifest.permission.ACCESS_FINE_LOCATION
    };

    GoogleMap map;
    LocationManager locationManager;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_location_map_exam);
        if(Build.VERSION.SDK_INT>=Build.VERSION_CODES.M){
            requestPermissions(permission_list,1000);
        }else{
            init();
        }
    }

    @Override
    public void onRequestPermissionsResult(int requestCode, @NonNull String[] permissions,
                                           @NonNull int[] grantResults) {
        super.onRequestPermissionsResult(requestCode, permissions, grantResults);
        for(int result:grantResults){
            if(result== PackageManager.PERMISSION_DENIED){
                return;
            }
        }
        init();
    }


    //맵정보 추출
    public void init(){
        //Map프레그먼트로 부터 맵을 얻기
        FragmentManager manager = getSupportFragmentManager();
        SupportMapFragment mapFragment = (SupportMapFragment)manager.findFragmentById(R.id.map);
        mapFragment.getMapAsync(this);

    }

    @Override
    public void onMapReady(GoogleMap googleMap) {
        map = googleMap;
        if(map!= null){
            getmyLocation();
        }


    }

    //location을 추출 - 현재 나의 위치정보를 추출
    public void getmyLocation(){
        locationManager = (LocationManager)getSystemService(LOCATION_SERVICE);
        if(Build.VERSION.SDK_INT>=Build.VERSION_CODES.M){
            for(String permission:permission_list){
                if(checkSelfPermission(permission)==PackageManager.PERMISSION_DENIED){
                    return;
                }
            }
        }

//이전에 측정했었던 값을 가져오고 - 새롭게 측정하는데 시간이 많이 걸릴 수 있으므로
        Location gps_loc =
                locationManager.getLastKnownLocation(LocationManager.GPS_PROVIDER);

        Location network_loc =
                locationManager.getLastKnownLocation(LocationManager.NETWORK_PROVIDER);

        if(gps_loc!=null){
            setmyLocation(gps_loc);
        }else{
            if(network_loc!=null){
                setmyLocation(network_loc);
            }
        }
        Log.d("myloc","===============================================");
        //현재 측정한 값도 가져온다.
        MyLocationListener locationListener =
                new MyLocationListener();
        //현재 활성화되어있는 Provider를 체크하는 작업
        // (locationManager가 무엇을 사용하고있는지 확인)
        if(locationManager.isProviderEnabled(LocationManager.GPS_PROVIDER)){
            //GPS_PROVIDER는 현재 내가 사용하고 있는 모듈
            locationManager.requestLocationUpdates(LocationManager.GPS_PROVIDER,
                    3000, 10, locationListener  );
            //몇 분에 한 번씩 체크할 것인지, 어느 거리마다 체크할 것인지
        }
        //GPS_PROVIDER가 활성화 되어있지 않으면, NETWORK_PROVIDER로 확인
        if(locationManager.isProviderEnabled(LocationManager.NETWORK_PROVIDER)){
            //GPS_PROVIDER는 현재 내가 사용하고 있는 모듈
            locationManager.requestLocationUpdates(LocationManager.NETWORK_PROVIDER,
                    3000, 10, locationListener  );
            //몇 분에 한 번씩 체크할 것인지, 어느 거리마다 체크할 것인지
        }
    }
    //location정보를 지도에 셋팅하는 메소드
    public void setmyLocation(Location myLocation){
        Log.d("myloc","위도"+myLocation.getLatitude());
        Log.d("myloc","경도"+myLocation.getLongitude());
        LatLng myloc = new LatLng(myLocation.getLatitude(),
                myLocation.getLongitude());
        CameraUpdate cameraUpdate = CameraUpdateFactory.newLatLngZoom(myloc,15);
        map.moveCamera(cameraUpdate);

        //현재위치를 포인트로 표시
        map.setMyLocationEnabled(true);


    }

    //클래스를 하나 만들어주었다.
    class MyLocationListener implements LocationListener{

        @Override
        public void onLocationChanged(Location location) {
            //현재 위도 경도가 변경되면 호출되는 메소드
            setmyLocation(location);
            //한 번만 받고 고정하고 싶다면? 리스너연결해제 문장을 추가한다.
            locationManager.removeUpdates(this);

        }

        @Override
        public void onStatusChanged(String provider, int status, Bundle extras) {

        }

        @Override
        public void onProviderEnabled(String provider) {

        }

        @Override
        public void onProviderDisabled(String provider) {

        }
    }


}

```



* activity_location_map_exam.xml

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
      xmlns:app="http://schemas.android.com/apk/res-auto"
      xmlns:tools="http://schemas.android.com/tools"
      android:layout_width="match_parent"
      android:layout_height="match_parent"
      >
      <fragment
          android:name="com.google.android.gms.maps.SupportMapFragment"
          android:layout_width="match_parent"
          android:layout_height="match_parent"
          android:id="@+id/map"/>
  </LinearLayout>
  ```