JFMinimalNotification
===========

This is an iOS UIView for presenting minimal notification view on both iPhone and iPad. JFMinimalNotification is only available in ARC and targets iOS 5.0+.

What It Looks Like:
------------------

### iPhone
New screen shots coming soon. For now, just clone and run the sample project. :)
<!-- ![Error With Right View](https://imageshack.us/a/img194/7325/screenshot20130508at125.png)
![Success With Left View](https://imageshack.us/a/img713/7325/screenshot20130508at125.png)
![Success](https://imageshack.us/a/img560/7325/screenshot20130508at125.png)
![Error](https://imageshack.us/a/img43/7325/screenshot20130508at125.png)
![Default](https://imageshack.us/a/img856/7325/screenshot20130508at125.png) -->

### iPad
<!-- ![Error With Right View](https://imageshack.us/a/img62/7325/screenshot20130508at125.png)
![Success With Left View](https://imageshack.us/a/img10/7325/screenshot20130508at125.png)
![Success](https://imageshack.us/a/img201/7325/screenshot20130508at125.png)
![Error](https://imageshack.us/a/img197/7325/screenshot20130508at125.png)
![Default](https://imageshack.us/a/img163/7325/screenshot20130508at125.png) -->

How To Use It:
-------------

### Basic Example

```objective-c
#import "JFMinimalNotification.h"

...

- (void)viewDidLoad
{
    [super viewDidLoad];
    
    /**
     * Create the notification
     */
    self.minimalNotification = [JFMinimalNotification notificationWithStyle:JFMinimalNotificationStyleDefault
                                                                      title:@"This is my awesome title"
                                                                   subTitle:@"This is my awesome sub-title"];
    
    /**
     * Set the desired font for the title and sub-title labels
     * Default is System Normal
     */
    UIFont* titleFont = [UIFont fontWithName:@"STHeitiK-Light" size:22];
    [self.minimalNotification setTitleFont:titleFont];
    UIFont* subTitleFont = [UIFont fontWithName:@"STHeitiK-Light" size:16];
    [self.minimalNotification setSubTitleFont:subTitleFont];

    /**
    * Add the notification to a view
    */
    [self.view addSubview:self.minimalNotification];
}

/**
 * Showing the notification from a button handler
 */
- (IBAction)show:(id)sender {
    [self.minimalNotification show];
}

/**
 * Hiding the notification from a button handler
 */
- (IBAction)dismiss:(id)sender {
    [self.minimalNotification dismiss];
}
```

### Constructors / Options
```objective-c
/**
 * Note: passing a dismissalDelay of 0 means the notification will NOT be automatically dismissed, you will need to 
 * dismiss the notification yourself by calling -dismiss on the notification object. If you pass a dismissalDelay 
 * value greater than 0, this will be the length of time the notification will remain visisble before being 
 * automatically dismissed.
 */
self.minimalNotification = [JFMinimalNotification notificationWithStyle:JFMinimalNotificationStyleError title:@"This is my awesome title" subTitle:@"This is my awesome sub-title" dismissalDelay:0.0 touchHandler:^{
    [self.minimalNotification dismiss];
}];
```

Please see the example project include in this repo for an example of how to use this notification.
    
Delegate Methods:
----------------

    - (void)willShowNotification:(JFMinimalNotification*)notification;
    - (void)didShowNotification:(JFMinimalNotification*)notification;
    - (void)willDisimissNotification:(JFMinimalNotification*)notification;
    - (void)didDismissNotification:(JFMinimalNotification*)notification;
    
Installation:
------------

### Add JFMinimalNotification to your project

- Simply copy the JFMinimalNotification folder containing the .h, .m, and .bundle files into your project.

### Add Dependencies

- In your application's project app target settings, find the "Build Phases" section and open the "Link Binary With Libraries" block
- Click the "+" button and select the "QuartzCore.framework".

License
-------
Copyright (c) 2012 Jeremy Fox ([jeremyfox.me](http://www.jeremyfox.me)). All rights reserved.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.