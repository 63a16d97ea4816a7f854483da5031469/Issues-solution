#Radius Boarder for UIImageView

        self.myimageView.image = [UIImage imageWithData:imageData];
        self.myimageView.layer.borderWidth = 3.0f;
        self.myimageView.layer.borderColor = [UIColor whiteColor].CGColor;
        self.myimageView.layer.cornerRadius=40;
        self.myimageView.clipsToBounds=YES;