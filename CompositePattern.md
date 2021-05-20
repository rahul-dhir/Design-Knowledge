**Composite strategy**
----------------------
1. Leaf and composite both have a is-a relationship to each other
2. Only the composite node has a has-a relationship with the leaf


we use composite patterns when we need to substitute 1 by many.

**STEPS**
-----

1. Start with strategy and turn it into composite.


Composite strategy is of 2 types
1. Design for uniformity
2. Design for type safety

**Example**
-------------

Abstract class Control{
  void Draw();
}

Class Textbox: Contro{
  public void Draw(){}
}

Class VScrollBarDecorator : Control {
  Control_target;
  public VScrollBarDecorator(Control target) {_target = target}
  Public void Draw()
  {
      //create vert scroll bar
      _target.Draw()
  }
}

lass HScrollBarDecorator : Control {
  Control_target;
  public HScrollBarDecorator(Control target) {_target = target}
  Public void Draw()
  {
      //create hori scroll bar
      _target.Draw()
  }
}



Public class program
{
  public static void main()
  {
    Control textBox = new Textbox();
    textbox.Draw();
    
    if(//)
      Control newTextbox = new HScrollBarDecorator(new VScrollBarDecorator(textbox));
      newTextbox.Draw();
  }
}
