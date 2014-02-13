DiffEqGrapher
=============

Differential Equation Grapher
So this isn't actually a readme, this is a note to george

=======
Operation classes handeled seperately, have public methods:
  double value(Point p)

======
Displayable Classes (implement Displayable)
Displayable itself has method
  public void drawTo( Drawable d);
Function
  simply has operation to get values and goes along 
GridDisplayable
  protected class GridIterator
    constructor accepts (Drawable d)
    protected Point getNext()
  protected abstract class NumericalSolution //May want to make regular class, not inner class
    constructor accepts (Drawable d)
    Uses Euler's method/R4K to draw num sol to plot numerical solution to d, without storing data
    Different implementation for slope and vector field
  
  extends to:
    SlopeField
      Uses GridIterator to cycle through points and display slope, within a box, at each point
      Has information about what order it is, must be able to work generally
    VectorField
      Cycles through and displays length and magnitude of vectors
  

======
Displaying classes
Drawable has information about what and where to draw

=OPTION 1:
Drawable is it's own class, which is changed for swing vs android
Probably simpler
=OPTION 2:
Drawable is an interface and is extended into swing implementations and adroid implementatiosn
Has benefit of allowing Drawable's instances to extend canvas/graphics/whatever

Drawable
  
