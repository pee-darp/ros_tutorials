<h1> What is URDF? </h1>
<p>URDF-Unified Robot Description Format- is an XML format for storing data about a robot. A robot can be broken down into two
main categories of bodies:
<ol><li>Links</li><li>Joints</li></ol>
Thus in any URDF we definitely find these two tags.</p>

<p>Each link and Joint further has some properties. To specifies these properties in URDF we make further use of tags. Following is
the minimal set of tags you need to know to make a basic robot:

<ol><li> origin - when used outside any other tags, it specifies the pose of the link's co-ordinate frame. When used inside visual 
or collision tags it specifies the pose of the visual or collision element of the link respectively.</li>
<li> visual - This tag is used to set the visual properties of the link.
  <ol><li> geometry - This tag is used to set the geometrical object that will be used for rendering the link. Different options like 
  box, cylinder, sphere are available. We can also use our own meshes by specifying a .dae or .stl file.</li>
  <li> material - This tag is used to give colour to the link.</li></ol></li>
  
  
      
