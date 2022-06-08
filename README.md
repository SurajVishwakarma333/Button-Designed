# Bounce Button Animation in Android.

• Go to the app -> res right click on res folder then New -> Android Resource Directory and create an anim Directory.

• Then right-click on anim folder then go to New -> Animation Resource File and create a bounce.xml file.

• bounce.xml file contains the animation which is used to animate the Button in the next step. The complete code for bounce.xml is given below.



            <?xml version="1.0" encoding="utf-8"?>
            <set
	       xmlns:android="http://schemas.android.com/apk/res/android"
	       android:fillAfter="true"
	       android:interpolator="@android:anim/bounce_interpolator">

	             <scale
		        android:pivotX="50%"
		        android:pivotY="50%"
		        android:fromXScale="0.5"
		        android:toXScale="1.0"
		        android:fromYScale="0.5"
		        android:toYScale="1.0"
		        android:duration="500"
	             </scale>		
            </set>


Now Go to the app -> res -> layout -> activity_main.xml file and add a simple Button, which we want to animate.


• Working with MainActivity.java file



        import android.os.Bundle;
        import android.view.View;
        import android.view.animation.Animation;
        import android.view.animation.AnimationUtils;
        import android.widget.Button;
        import androidx.appcompat.app.AppCompatActivity;

        public class MainActivity extends AppCompatActivity {
	
      	@Override
      	protected void onCreate(Bundle savedInstanceState) {
		    super.onCreate(savedInstanceState);
		    setContentView(R.layout.activity_main);
		
		    // loading Animation from
		    final Animation animation = AnimationUtils.loadAnimation(this, R.anim.bounce);

		    // getting the Button from activity_main.xml file
		    final Button button = findViewById(R.id.button);
		    button.setOnClickListener(new View.OnClickListener() {
			  @Override
			   public void onClick(View view) {
				 // start the animation
				 button.startAnimation(animation);
			   }
	           });
	  }
      }

https://user-images.githubusercontent.com/101108540/172102689-062ac010-7bab-47de-9f45-826179a3476e.mp4    
# Fluorescent Colors Button   

• right click on drawable -> new -> Drawable Resource File

• Give file name eg: button_design

• It will generate button_design.xml
Write the below code in button_design.xml file.




        <?xml version="1.0" encoding="utf-8"?>
	    <selector xmlns:android="http://schemas.android.com/apk/res/android">
    	   <item>
             <layer-list>
                <item android:right="5dp" android:top="5dp">
                    <shape>
                    	<corners android:radius="3dp" />
                    	<solid android:color="#00FFDF" />
               	    </shape>
                </item>
              <item android:bottom="2dp" android:left="2dp">
                   <shape>
                        <gradient android:angle="270"
			android:endColor="#9BFFF8" android:startColor="#00F9FF" />
                    	<stroke android:width="1dp" android:color="#4EFFFF" />
                    	<corners android:radius="4dp" />
                    	<padding android:bottom="10dp" android:left="10dp"
                        android:right="10dp" android:top="10dp" />
                   </shape>
                </item>
             </layer-list>
          </item>
        </selector>
	


• Now Go to the app -> res -> layout -> activity_main.xml file and add a simple Button, which we want to animate.


	
	<Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:background="@drawable/buttondesign"  //Remember to add this line 
        android:text="Color"
        </Button>



![FluorescentButton](https://user-images.githubusercontent.com/101108540/172101683-498610db-e13c-4c71-bafa-38cfaad44dd0.png)




# IF FACING PROBLEMS LIKE BUTTON COLOR IS NOT UPDATING/CHANGING TRY THIS BOTH WILL WORK.

# Solution 1:

![ButtonColorsChange](https://user-images.githubusercontent.com/101108540/172105086-dbc66aab-3223-4122-a107-fcbc75d82c87.jpg)


# Solution 2:  

![buttoncolorchange](https://user-images.githubusercontent.com/101108540/172105089-2dcde188-b4d0-4f03-831c-9890c3208e50.jpg)
