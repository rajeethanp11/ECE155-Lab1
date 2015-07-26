package ca.uwaterloo.Lab1_201_11;

import java.util.Arrays;

import android.support.v7.app.ActionBarActivity;
import android.support.v7.app.ActionBar;
import android.support.v4.app.Fragment;
import android.graphics.Color;
import android.hardware.Sensor;
import android.hardware.SensorEvent;
import android.hardware.SensorEventListener;
import android.hardware.SensorManager;
import android.os.Bundle;
import android.view.LayoutInflater;
import android.view.Menu;
import android.view.MenuItem;
import android.view.View;
import android.view.ViewGroup;
import android.widget.LinearLayout;
import android.widget.TextView;
import android.os.Build;







public class MainActivity extends ActionBarActivity {
	



	@Override
	protected void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.activity_main);
		if (savedInstanceState == null) {
			getSupportFragmentManager().beginTransaction()
			.add(R.id.container, new PlaceholderFragment())
			.commit();
		}
	}


	@Override
	public boolean onCreateOptionsMenu(Menu menu) {
		// Inflate the menu; this adds items to the action bar if it is present.
		getMenuInflater().inflate(R.menu.main, menu);
		return true;
	}

	@Override
	public boolean onOptionsItemSelected(MenuItem item) {
		// Handle action bar item clicks here. The action bar will
		// automatically handle clicks on the Home/Up button, so long
		// as you specify a parent activity in AndroidManifest.xml.
		int id = item.getItemId();
		if (id == R.id.action_settings) {
			return true;
		}
		return super.onOptionsItemSelected(item);
	}

	
	
	/**
	 * A placeholder fragment containing a simple view.
	 */
	public static class PlaceholderFragment extends Fragment {
      ;
	//LineGraphView graph;	
		public PlaceholderFragment() {
		}

		@Override
		public View onCreateView(LayoutInflater inflater, ViewGroup container,
				Bundle savedInstanceState) {
			View rootView = inflater.inflate(R.layout.fragment_main, container, false);
            LinearLayout layout = (LinearLayout) rootView.findViewById(R.id.label2);
          
   //sets layout to vertical
            
            layout.setOrientation(LinearLayout.VERTICAL);
            
            //LineGraphView object creation
            
            LineGraphView graph = new LineGraphView(rootView.getContext(),100,Arrays.asList("x","y","z"));
            layout.addView(graph);
            graph.setVisibility(View.VISIBLE);
            
            //Redundant code Please remove afterwards
            
            //TextView tv = (TextView) rootView.findViewById(R.id.label1);
			//tv.setText("I’ve replaced the label!");
			//TextView tv1 = new TextView(rootView.getContext());
			//tv1.setText("Example Text");
			//tv1.findViewById(R.id.label2);
			//layout.addView(tv1);
			
            //Redundant code Please remove afterwards
            
            //Light Sensor Starts
            
            TextView lightSensorHeading = new TextView(rootView.getContext());
            lightSensorHeading.setText("---   LIGHT INTENSITY   ---");
            layout.addView(lightSensorHeading);
            
			TextView lightSensorVariable = new TextView(rootView.getContext());
			lightSensorVariable.setText("TEST FOR LIGHT");
			layout.addView(lightSensorVariable);
			
			//Max value object creation for Light Sensor
			
			TextView lightMaxValue = new TextView(rootView.getContext());
			lightMaxValue.setText("Max value for light");
			layout.addView(lightMaxValue);
			
			
			SensorManager sensorManager = (SensorManager) rootView.getContext().getSystemService(SENSOR_SERVICE);
            Sensor lightSensor = sensorManager.getDefaultSensor(Sensor.TYPE_LIGHT);
            SensorEventListener l = new LightSensorEventListener(lightSensorHeading, lightSensorVariable, lightMaxValue);
            sensorManager.registerListener(l, lightSensor, SensorManager.SENSOR_DELAY_NORMAL);
            
            //Light sensor Ends
            
            //Accelerometer Starts
            
            TextView accelerationvector = new TextView(rootView.getContext());
            accelerationvector.setTextColor(Color.parseColor("#FF0000"));
            accelerationvector.setText("---  RECORD ACCELERATION (linear) (m/s^2)  --- ");
            layout.addView(accelerationvector);
            
            TextView accelerometerx = new TextView(rootView.getContext());
            accelerometerx.setText("X :");
            layout.addView(accelerometerx);
            
            TextView accelerometery = new TextView(rootView.getContext());
            accelerometery.setText("Y :");
            layout.addView(accelerometery);
            
            TextView accelerometerz = new TextView(rootView.getContext());
            accelerometerz.setText("Z :");
            layout.addView(accelerometerz);
            
            //Object creation for maximum values of accelerometer
            
            TextView max_xcoordinate = new TextView(rootView.getContext());
            max_xcoordinate.setText("max value x : ");
            layout.addView(max_xcoordinate);
            
            TextView max_ycoordinate = new TextView(rootView.getContext());
            max_ycoordinate.setText("max value y : ");
            layout.addView(max_ycoordinate);
            
            TextView max_zcoordinate = new TextView(rootView.getContext());
            max_zcoordinate.setText("max value z : ");
            layout.addView(max_zcoordinate);
            
            Sensor AccelerometerSensor = sensorManager.getDefaultSensor(Sensor.TYPE_ACCELEROMETER);
            SensorEventListener a = new accelerometer(accelerometerx, accelerometery, accelerometerz, graph, max_xcoordinate, max_ycoordinate, max_zcoordinate);
            sensorManager.registerListener(a, AccelerometerSensor, SensorManager.SENSOR_DELAY_NORMAL);
            
            //Accelerometer ends
            
            //Magnetic field starts
            
            TextView magneticFieldVariable = new TextView(rootView.getContext());
            magneticFieldVariable.setTextColor(Color.parseColor("#FF0000"));
            magneticFieldVariable.setText("---   MAGNETIC FIELD VALUES   ---");
            layout.addView(magneticFieldVariable);
            
            TextView magneticFieldVariablex = new TextView(rootView.getContext());
            magneticFieldVariablex.setText("X :");
            layout.addView(magneticFieldVariablex);
            
            TextView magneticFieldVariabley = new TextView(rootView.getContext());
            magneticFieldVariabley.setText("Y :");
            layout.addView(magneticFieldVariabley);
            
            TextView magneticFieldVariablez = new TextView(rootView.getContext());
            magneticFieldVariablez.setText("Z :");
            layout.addView(magneticFieldVariablez);
            
            //Object Creation for maximum values for magnetic field
            
            TextView magneticMax_xcoordinate = new TextView(rootView.getContext());
            magneticMax_xcoordinate.setText("Magnetic max x : ");
            layout.addView(magneticMax_xcoordinate);
            
            TextView magneticMax_ycoordinate = new TextView(rootView.getContext());
            magneticMax_ycoordinate.setText("Magnetic max y : ");
            layout.addView(magneticMax_ycoordinate);
            
            TextView magneticMax_zcoordinate = new TextView(rootView.getContext());
            magneticMax_zcoordinate.setText("Magnetic max x : ");
            layout.addView(magneticMax_zcoordinate);
            
            Sensor magneticFieldSensor = sensorManager.getDefaultSensor(Sensor.TYPE_MAGNETIC_FIELD);
            SensorEventListener m = new MagneticFieldSensorEventListener(magneticFieldVariablex, magneticFieldVariabley, magneticFieldVariablez, magneticMax_xcoordinate, magneticMax_ycoordinate, magneticMax_zcoordinate);
            sensorManager.registerListener(m, magneticFieldSensor, SensorManager.SENSOR_DELAY_NORMAL);
            
            //Magnetic field ends
            
            //Rotation vector starts
            
            TextView rotationvector = new TextView(rootView.getContext());
            rotationvector.setTextColor(Color.parseColor("#FF0000"));
            rotationvector.setText("---    ROTATION VECTOR VALUES    ---");
            layout.addView(rotationvector);
            
            TextView rotationvectorx = new TextView(rootView.getContext());
            rotationvectorx.setText("X :");
            layout.addView(rotationvectorx);
            
            TextView rotationvectory = new TextView(rootView.getContext());
            rotationvectory.setText("Y :");
            layout.addView(rotationvectory);
            
            TextView rotationvectorz = new TextView(rootView.getContext());
            rotationvectorz.setText("Z :");
            layout.addView(rotationvectorz);
            
            //Object creation for maximum values of Rotation Vector
            
            TextView RotationMax_x = new TextView(rootView.getContext());
            RotationMax_x.setText("Max x coordinate : ");
            layout.addView(RotationMax_x);
            
            TextView RotationMax_y = new TextView(rootView.getContext());
            RotationMax_y.setText("Max y coordinate : ");
            layout.addView(RotationMax_y);
            
            TextView RotationMax_z = new TextView(rootView.getContext());
            RotationMax_z.setText("Max z coordinate : ");
            layout.addView(RotationMax_z);
            
            Sensor RotationVectorSensor = sensorManager.getDefaultSensor(Sensor.TYPE_ROTATION_VECTOR);
            SensorEventListener r = new RotationVector(rotationvectorx, rotationvectory, rotationvectorz, RotationMax_x, RotationMax_y, RotationMax_z);
            sensorManager.registerListener(r, RotationVectorSensor, SensorManager.SENSOR_DELAY_NORMAL);
            
            //Rotation Vector ends
           
            
			return rootView;
		}
	}
}


class LightSensorEventListener implements SensorEventListener {
	
	LineGraphView graph;
	TextView output;
	TextView headerLight;
	TextView maxLight;
	float max_light = -800;
	
	public LightSensorEventListener(TextView heading, TextView outputView, TextView LightMaxIntensity){
		
		output = outputView;
		headerLight = heading;
		maxLight = LightMaxIntensity;
		
	}
	public void onAccuracyChanged(Sensor s, int i) {}

	public void onSensorChanged(SensorEvent se) {
		if (se.sensor.getType() == Sensor.TYPE_LIGHT) {
			
			String light = String.format("%f", se.values[0]);
			headerLight.setTextColor(Color.parseColor("#FF0000"));
			output.setText("Light Intensity :  " + light);
			if(se.values[0] > max_light)
			{
				max_light = se.values[0];
				max_light = Math.abs(max_light);
				maxLight.setTextColor(Color.parseColor("#0000CC"));
				maxLight.setText("Max value of light is : " + String.valueOf(max_light) + "\n");
			}
	}
 }
}
class accelerometer implements SensorEventListener {
	TextView output;
	TextView accelerometerx;
	TextView accelerometery;
	TextView accelerometerz;
	LineGraphView graphtest;
	TextView max_x;
	TextView max_y;
	TextView max_z;
	float max_xvariable = -800;
	float max_yvariable = -800;
	float max_zvariable = -800;
	public accelerometer(TextView accelerometerxvariable, TextView accelerometeryvariable, TextView accelerometerzvariable, LineGraphView graphCopy, TextView max_xcoordinate, TextView max_ycoordinate, TextView max_zcoordinate) {
       
		accelerometerx = accelerometerxvariable;
		accelerometery = accelerometeryvariable;
		accelerometerz = accelerometerzvariable;
		graphtest = graphCopy;
		max_x = max_xcoordinate;
		max_y = max_ycoordinate;
		max_z = max_zcoordinate;
	}
	
	public void onAccuracyChanged(Sensor S, int i) {}
	
	public void onSensorChanged(SensorEvent se) {
		
		//Putting the values of "se.values" array into a float array in order 
		//to pass it to the addPoint method of LineGraphView.java which takes in a 
		//float array as an argument
		
		float[] myArray = new float[3];
		myArray[0] = se.values[0];
		myArray[1] = se.values[1];
		myArray[2] = se.values[2];
		if(se.sensor.getType() == Sensor.TYPE_ACCELEROMETER) {
			
			String x = String.format("%f", se.values[0]);
			accelerometerx.setText("X Coordinate: " + x);
			String y = String.format("%f", se.values[1]);
			accelerometery.setText("Y Coordinate: " + y);
			String z = String.format("%f", se.values[2]);
			accelerometerz.setText("Z Coordinate: " + z + "\n");
			if(myArray[0] > max_xvariable)
			{
				max_xvariable = myArray[0];
				max_xvariable = Math.abs(max_xvariable);
				max_x.setTextColor(Color.parseColor("#0000CC"));
				max_x.setText("Max X coordinate: " + String.valueOf(max_xvariable));
			}
			if(myArray[1] > max_yvariable)
			{
				max_yvariable = myArray[1];
				max_yvariable = Math.abs(max_yvariable);
				max_y.setTextColor(Color.parseColor("#0000CC"));
				max_y.setText("Max Y coordinate: " + String.valueOf(max_yvariable));
			}
			if(myArray[2] > max_zvariable)
			{
				max_zvariable = myArray[2];
				max_zvariable = Math.abs(max_zvariable);
				max_z.setTextColor(Color.parseColor("#0000CC"));
				max_z.setText("Max Z coordinate: " + String.valueOf(max_zvariable) + "\n");
			}
			//adds the respective points to the graph using the addpoint method
			graphtest.addPoint(myArray);
		}
		
	}

}
 class RotationVector implements SensorEventListener {
	TextView output;
	TextView rotationx;
	TextView rotationy;
	TextView rotationz;
	TextView RotationMax_x;
	TextView RotationMax_y;
	TextView RotationMax_z;
	float max_xvariable = -800;
	float max_yvariable = -800;
	float max_zvariable = -800;
	
	public RotationVector(TextView rotationxvariable, TextView rotationyvariable, TextView rotationzvariable, TextView rotationmax_xvariable, TextView rotationmax_yvariable, TextView rotationmax_zvariable) {
		rotationx = rotationxvariable;
		rotationy = rotationyvariable;
		rotationz = rotationzvariable;
		RotationMax_x = rotationmax_xvariable;
		RotationMax_y = rotationmax_yvariable;
		RotationMax_z = rotationmax_zvariable;
	}
	
	public void onAccuracyChanged (Sensor S, int i) {}
	
	public void onSensorChanged(SensorEvent se) {
		if(se.sensor.getType() == Sensor.TYPE_ROTATION_VECTOR) {
			String x = String.format("%f", se.values[0]);
			rotationx.setText("X Coordinate: " + x);
			String y = String.format("%f", se.values[1]);
			rotationy.setText("Y Coordinate: " + y);
			String z = String.format("%f", se.values[2]);
			rotationz.setText("Z Coordinate: " + z + "\n");
			if(se.values[0] > max_xvariable)
			{
				max_xvariable = se.values[0];
				max_xvariable = Math.abs(max_xvariable);
				RotationMax_x.setTextColor(Color.parseColor("#0000CC"));
				RotationMax_x.setText("Max X coordinate : " + String.valueOf(max_xvariable));
			}
			if(se.values[1] > max_yvariable)
			{
				max_yvariable = se.values[1];
				max_yvariable = Math.abs(max_yvariable);
				RotationMax_y.setTextColor(Color.parseColor("#0000CC"));
				RotationMax_y.setText("Max Y coordinate : " + String.valueOf(max_yvariable));
			}
			if(se.values[2] > max_zvariable)
			{
				max_zvariable = se.values[2];
				max_zvariable = Math.abs(max_zvariable);
				RotationMax_z.setTextColor(Color.parseColor("#0000CC"));
				RotationMax_z.setText("Max Z coordinate : " + String.valueOf(max_zvariable) + "\n");
			}
		}
	}
}

class MagneticFieldSensorEventListener implements SensorEventListener {
	TextView output;
	TextView outputx;
	TextView outputy;
	TextView outputz;
	TextView MagneticMax_x;
	TextView MagneticMax_y;
	TextView MagneticMax_z;
	float max_xvariable = -800;
	float max_yvariable = -800;
	float max_zvariable = -800;
	
	public MagneticFieldSensorEventListener(TextView outputxvariable, TextView outputyvariable, TextView outputzvariable, TextView magneticMax_xcoordinate, TextView magneticMax_ycoordinate, TextView magneticMax_zcoordinate) {
		outputx = outputxvariable;
		outputy = outputyvariable;
		outputz = outputzvariable;
		MagneticMax_x = magneticMax_xcoordinate;
		MagneticMax_y = magneticMax_ycoordinate;
		MagneticMax_z = magneticMax_zcoordinate;
	}
	
	public void onAccuracyChanged(Sensor s, int i) {}
	
	public void onSensorChanged(SensorEvent se) {
	  if(se.sensor.getType() == Sensor.TYPE_MAGNETIC_FIELD) {
		  
		  String x = String.format("%f", se.values[0]);
		  outputx.setText("X Coordinate : " + x);
		  String y = String.format("%f", se.values[1]);
		  outputy.setText("Y Coordinate : " + y);
		  String z = String.format("%f", se.values[2]);
		  outputz.setText("Z Coordinate : " + z + "\n");
		  if(se.values[0] > max_xvariable)
		  {
			  max_xvariable = se.values[0];
			  //max_xvariable = Math.abs(max_xvariable);
			  MagneticMax_x.setTextColor(Color.parseColor("#0000CC"));
			  MagneticMax_x.setText("Max X coordinate is : " + String.valueOf(Math.abs(max_xvariable)));
		  }
		  if(se.values[1] > max_yvariable)
		  {
			  max_yvariable = se.values[1];
			  //max_yvariable = Math.abs(max_yvariable);
			  MagneticMax_y.setTextColor(Color.parseColor("#0000CC"));
			  MagneticMax_y.setText("Max Y coordinate is : " + String.valueOf(Math.abs(max_yvariable)));
		  }
		  if(se.values[2] > max_zvariable)
		  {
			  max_zvariable = se.values[2];
			  //max_zvariable = Math.abs(max_zvariable);
			  MagneticMax_z.setTextColor(Color.parseColor("#0000CC"));
			  MagneticMax_z.setText("Max Z coordinate is : " + String.valueOf(Math.abs(max_zvariable)) + "\n");
		  }
		  
	}
	}

}



