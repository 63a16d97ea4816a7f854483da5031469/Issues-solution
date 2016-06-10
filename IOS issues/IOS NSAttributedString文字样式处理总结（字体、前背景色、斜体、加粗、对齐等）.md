##IOS NSAttributedString文字样式处理总结（字体、前背景色、斜体、加粗、对齐等）

http://simayang.com/archives/533.html

    NSMutableAttributedString* str = [[NSMutableAttributedString alloc]init];
    //1.设置前景色与字体大小 
    NSAttributedString* tmpStr = [[NSAttributedString alloc] initWithString:@"这是红色文字并"
                    attributes:@{
                        NSFontAttributeName: [UIFont systemFontOfSize:18],
                        NSForegroundColorAttributeName:[UIColor redColor]
                    }];
    [str appendAttributedString:tmpStr];
    
    //2.斜体
    CGAffineTransform matrix =  CGAffineTransformMake(1, 0, tanf(15 * (CGFloat)M_PI / 180), 1, 0, 0);
    UIFontDescriptor *desc = [ UIFontDescriptor fontDescriptorWithName :[ UIFont systemFontOfSize :18 ]. fontName matrix :matrix];
    UIFont* italicFont= [ UIFont fontWithDescriptor :desc size :18];
    
    tmpStr = [[NSAttributedString alloc] initWithString:@"斜体" attributes:@{
                        NSFontAttributeName: italicFont,
                        NSForegroundColorAttributeName:[UIColor redColor]
                    }];
    [str appendAttributedString:tmpStr];
    
    //3.加粗
    tmpStr = [[NSAttributedString alloc] initWithString:@"加粗" attributes:@{
                        NSFontAttributeName: [UIFont boldSystemFontOfSize:18],
                        NSForegroundColorAttributeName:[UIColor redColor]
    }];
    [str appendAttributedString:tmpStr];
    
    NSString* rangeStr = @" 另外这是一条带背景色的下划线，最后是一条删除线";
    NSMutableAttributedString* attributeString = [[NSMutableAttributedString alloc]initWithString:rangeStr];
    //设置字体与背景色
    [attributeString addAttribute:NSFontAttributeName value:[UIFont systemFontOfSize:18 ] range:NSMakeRange(0, 12)];
    [attributeString addAttribute:NSBackgroundColorAttributeName value:[UIColor grayColor] range:NSMakeRange(0, 12)];
    //4.加上下划线
    [attributeString addAttribute:NSUnderlineStyleAttributeName value:[NSNumber numberWithInt:1] range:NSMakeRange(12,3)];
    //5.设置删除线
    [attributeString addAttribute: NSStrikethroughStyleAttributeName value:[NSNumber numberWithInt:1] range:NSMakeRange(16,8)];
    [str appendAttributedString:attributeString];