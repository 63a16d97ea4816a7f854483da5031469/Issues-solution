#CocoaPods - required a higher minimum deployment target

pod install --verbose

[!] Unable to satisfy the following requirements:

- `AFNetworking (~> 2.6)` required by `Podfile`
- `AFNetworking (= 2.6.3)` required by `Podfile.lock`

Specs satisfying the `AFNetworking (~> 2.6), AFNetworking (= 2.6.3)` dependency were found, but they required a higher minimum deployment target.



Changed to 

pod update --verbose

it is solved.