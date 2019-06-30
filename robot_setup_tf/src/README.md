<h1>What is tf?</h1>

<p>In robotics, we usually have to deal with a lot of moving parts. A robot is just that - Many rigid bodies connected using joints.
Take as an example, a four wheeled robot with a robotic arm. Further suppose that we need to grip an object and we have a camera at
the end of the manipulator which gives us the co-ordinates of the object.</p>

<p> The problem at hand now is how to specify the co-ordinates of the object in terms of the robot base instead of the camera.
When reframed the above question is posed as: How to represent the co-ordinates of the object in the robot base 'co-ordinate frame'
instead of the camera's 'co-ordinate frame'?.</p>

>Answer: Transformation

<p>Transformation is a set of mathematical operations (linear algebra alert!) carried out on the position vector of the object (as seen
from camera Co-ordinate frame) to get the position of the object as will be seen from the robot base frame. We could choose to do this
piece of mathematics by hand but a smarter way of doing it is using the tf software library.</p>

><p> The tf library gives us a set of classes whose objects can be used to:
 ><ol>
 ><li>Compute this transformation between any two specified co-ordinate frames (eg: in our case these frames would be camera frame and base frame)</li>
 ><li>Publish this result the ROS computation graph</li>
 ><li>Listen to such transformations sent over the ROS computation graph by different transform broadcasters.
 ></ol>
 
 
 <h1>Code Explanation</h1>
 
 <h2>tf_broadcaster.cpp</h2>
 
 <p> The main include file is tf_broadcaster.h. We initialize the node and create the broadcaster object. We then send the transform
 as a set of Quaternion and Vector3 data structures with time stamp and frame names between which the transform is taking place.</p>
 <p>We can send tranforms between different frames in this same cpp file using different broadcaster objects.</p>
 
 >Try to write a cpp code to send transforms between successive links of a manipulator of your choice. (ex:RhinoXR3)
 
 <h2>tf_listener.cpp</h2>
 
 <p>The main include file here is the transform_listener.h. We write a function which takes a listener object as an argument. This object
 offers a function named transformPoint() which takes three arguments:
 <ol>
 <li>Name of the frame to which the point is transformed. </li>
 <li>Name of the point to be transformed. </li>
 <li>Name of the storage point </li>
 </ol>
 </p>
 
 <p> A ROS timer object is used to call this function every second. Thus, inside the Transform Point function we can store the
 transform of a particular point in different storage points. </p>

 
