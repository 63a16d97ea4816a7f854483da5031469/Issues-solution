##setAdjustsFontSizeToFitWidth

For delivery string, the string font size and font name is different for different cases. In order to make it be fit to the width all the time, I used below sentences:
[header.deliveryString setNumberOfLines:1];
[header.deliveryString setAdjustsFontSizeToFitWidth:YES];


I seached online and find this below:

[Label setAdjustsLetterSpacingToFitWidth:YES];
[Label setMinimumScaleFactor:2];
[Label setAdjustsFontSizeToFitWidth:YES];


In addition to what the other answers say, if you put minSize/defaultSize (division) as the minimumScaleFactor, it will be the same as using the old minimumFontSize.

Ex, if you want the minimum font size to be 10 using default label size, you can do:

[label setMinimumScaleFactor:10.0/[UIFont labelFontSize]];

(Replace [UIFont labelFontSize] with your label's font size if it is not the default).

which would be the same as: [label setMinimumFontSize:10.0];

