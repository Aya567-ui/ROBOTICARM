#explantion :
  the DH METHOD is used to calculate the transformation matrix of each joint given its parameters 

   we get then the transformation matrix of each joint and multiply them inorder to get the total transformation

matrix

  inverse kinematics :(equations are found also in the lab report)

    we calculate the angles q1, q21, q31, q41 by knowing the coordinates of our target point note that 
   q41 is the wrist angle which in our 4 dof robotic arm was constant but we planned on adding 
    it in the simulation

 forward kinematics:
 forward kinematics equations calculate the position of the joints given the angles 
x1 x2..., y1,y2,.... z1,z2,...   note: x1=0 y1=0 since these are corresponding to the base which is plotted at center O 
\now we need to combine these to get to plot the arm

a way to understand this is that x3 y3 z3 are the coordinated of the end point of the elbow (2nd limk)
x2 y2 z2 .... of the shoulder  and so on 

Now we combine them like that note that the first element is zero because it corresponds to the base x which is fixed 
to the origin 
x = [0, x1, x2, x3, x4];
y = [0, y1, y2, y3, y4];
z = [0, z1, z2, z3, z4];

the reason for putting these vectors like that is it is used for plotting the links :

for i = 1:length(x) - 1
    line([x(i), x(i + 1)], [y(i), y(i + 1)], [z(i), z(i + 1)], ...)

here we plot every link using this for loop 


Note: we did not use the transformation matrices to plot the arm because we instead used the method above 
 
what is the transformation matrix about ? 
well the  transfromation matrices tells us the orientation (position) of the a certain certain part w,.r.t the one after 
it. so for example the forarm with respect to the base and so on. when the base is moved the forearm position is changed 
and so to account for it e need thi transformation matrix . now inorder to know the position the last element (gripper)
 we multiply all the matrices . 

We calculate it based on 4 parameters — called the Denavit-Hartenberg (D-H) parameters. These are defined for each joint of the robot.
    










