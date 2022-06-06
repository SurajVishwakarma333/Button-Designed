# Bounce Animation in Android.

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
		            android:duration="500"/>
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
