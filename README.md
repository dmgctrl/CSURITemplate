CSURITemplate
=============

[![Build Status](https://travis-ci.org/cogenta/CSURITemplate.png?branch=master)](https://travis-ci.org/cogenta/CSURITemplate)

CSURITemplate is an Objective-C implementation of
[RFC6570: URI Template](http://tools.ietf.org/html/rfc6570) up to Level 4 of
the spec.

Example usage:

```objc
NSError *error = nil;
CSURITemplate *template = [CSURITemplate URITemplateWithString:@"{?list*}"
                                                         error:&error];
NSDictionary *variables = @{@"list": @[@"red", @"green", @"blue"]};
NSString *uri = [template relativeStringWithVariables:variables];
assert([uri isEqualToString:@"?list=red&list=green&list=blue"]);
```

Installation
------------

[CocoaPods](http://cocoapods.org/) is the easiest way to use CSURITemplate.

    platform :ios, '6.0'
    pod 'CSURITemplate'
