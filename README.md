# A-Note-on-Coding-issues
This repository mainly focus on solution for tiny little coding issue that similar to stack overflow question post

######1.Converting UnixMilli TimeStamp: timeStamp = 1458162392920
```
a. long long currentTime = (long long)([[NSDate date] timeIntervalSince1970] * 1000.0);
b. UnixMilliseconds back to current date
- (NSString *)convertUnixMilliTimeStampIntoDate:(NSNumber *) unixTimeStamp {
    NSTimeInterval timeInterval = [unixTimeStamp doubleValue];
    NSDate *date = [NSDate dateWithTimeIntervalSince1970:timeInterval/1000];
    
    NSDateFormatter *dateFormatter = [[NSDateFormatter alloc] init];
    [dateFormatter setLocale:[NSLocale currentLocale]];
    [dateFormatter setDateFormat: @"y-M-d'T'H:m:s.SSS'Z'"];  //based on the server json return date format
    
    return  [dateFormatter stringFromDate:date];
}
```
#####2. Alamofire 3.0 & SwiftJSON 2.3.0
