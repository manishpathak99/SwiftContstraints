
The attached code contains functions for simplifying the constraint development process in Swift 2.

The existing way to build a constraint is cumbersome at best.

You can use the attached file first creating a Constraint relationship, which is either a restricted view to an authority view, or a restricted view to itself.  The views can be any UIView object, like a table, button, label, uiview, etc.  Then you can chain all the contraints you, defining their parameters at that time.  If there is an error in the constraint or a conflict, the error will show the name of the constraint, the setting, and the file, function, and line that caused it.


The NSLayoutAttribute, which are list below, is an enum and easy to set:

.Baseline
.Bottom
.BottomMargin
.CenterX
.CenterXWithinMargins
.CenterY
.CenterYWithinMargins
.FirstBaseline
.Height
.Leading
.LeadingMargin
.Left
.LeftMargin
.Right
.RightMargin
.Top
.TopMargin
.Trailing
.TrailingMargin
.Width



var view1 = UIView() 

Constraint(restricted:view1, authority:self)


All the settings take an NSLayoutAttribute, the Fixed ones require a constant (NSNumber) and the Relative ones a multiplier (NSNumber)

.equal(_attribute:)
.equalAlterFixed(_attribute:, constant _constant:)
.equalAlterRelative(_attribute:, multiple _multiple:)

.staticWidth(_constant:)
.staticHeight(_constant:)

.squareStatic(_value:)
.lineStaticWidth(_constant:)
.lineStaticHeight(_constant:)


.greaterOrSame(_attribute:)
.greaterOrSameAlterFixed(_attribute:, constant _constant:)
.greaterOrSameAlterRelative(_attribute:, multiple _multiple:)

.lessOrSame(_attribute:)
.lessOrSameAlterFixed(_attribute:, constant _constant:Int)
.lessOrSameAlterRelative(_attribute:, multiple _multiple:)

.relateEqual(_authority:, restrict _restricted:)
.relateEqualAlterFixed(_authority:, restrict _restricted:, constant _constant:)
.relateEqualAlterRelative(_authority:, restrict _restricted:, multiple _multiple:)

.relateLessOrEqual(_authority:, restrict _restricted:)
.relateLessOrEqualAlterFixed(_authority:, restrict _restricted:, constant _constant:)
.relateLessOrEqualAlterRelative(_authority:, restrict _restricted:, multiple _multiple:Float)

.relateGreaterOrEqual(_authority:, restrict _restricted:)
.relateGreaterOrEqualAlterFixed(_authority:, restrict _restricted:, constant _constant:Int)
.relateGreaterOrEqualAlterRelative(_authority:, restrict _restricted:, multiple _multiple:Float)

.lineRelativeWidth(multiple _multiple:)
.lineRelativeHeight(multiple _multiple:)
.rectangleRelative(height _height:, width _width:)
.rectangleStatic(height _height:, width _width:)

.matchAll()

.insetStatic(leading _leading:, trailing _trailing:, top _top:, bottom _bottom:)

.insetRelative(leading _leading:, trailing _trailing:, top _top:, bottom _bottom:)
.insetMargin()
.insetUniformStatic(_constant:)
.insetUniformRelative(_multiple:)

















