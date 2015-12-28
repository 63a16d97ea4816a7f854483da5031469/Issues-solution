#UITextField unable to become first responder if added to UITableViewCell via accessoryView

 
Use this one:

    [cell.textField becomeFirstResponder];


But make sure others do not have this "becomeFirstResponder". Otherwise, it will conflict....(without showing any warning or errors).




http://www.makemegeek.com/implement-uitextfield-ios/
 