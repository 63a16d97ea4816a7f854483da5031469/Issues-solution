#When is -[UIView drawRect:] Method Invoked?

It's called whenever the view or part of the view needs to be drawn or redrawn.

It's called when you first display the view. It's called when you alter the view. In the life cycle of a view, it may be called hundreds or even thousands of times. For example, in a text view, it is called every time a new text character is entered.

Any change in the program state that the view must reflect visually should trigger a redraw by calling setNeedsDisplay. This happens automatically in most cases but you may need to trigger it yourself if you do something non-standard.

	[View setNeedsDisplay];