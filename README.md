# ElasticTransition

[![Version](https://img.shields.io/cocoapods/v/ElasticTransition.svg?style=flat)](http://cocoapods.org/pods/ElasticTransition)
[![License](https://img.shields.io/cocoapods/l/ElasticTransition.svg?style=flat)](http://cocoapods.org/pods/ElasticTransition)
[![Platform](https://img.shields.io/cocoapods/p/ElasticTransition.svg?style=flat)](http://cocoapods.org/pods/ElasticTransition)

A UIKit custom modal transition that simulates an elastic drag. Written in Swift.

![demo](https://github.com/lkzhao/ElasticTransition/blob/master/demo.gif?raw=true)

## Usage

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Requirements

* Xcode 7 or higher
* iOS 9.0 or higher (Update is coming to support lower versions)
* ARC
* Swift 2.0

## Installation

####CocoaPods

```ruby
pod "ElasticTransition"
```

####Manual

Clone and add ElasticTransition folder into your project.

## Example

##### 1. in your view controller
```

  var transition = ElasticTransition()
  override func viewDidLoad() {
    super.viewDidLoad()

    // this setup the pan gesturerecognizer & transition delegate
    transition.backViewController = self
    transition.segueIdentifier = "menu" // supplied segue is triggered when drag start

    // customization
    transition.sticky = false
    transition.panThreshold = 0.3
    transition.fancyTransform = false
    // ...
  }

  override func prepareForSegue(segue: UIStoryboardSegue, sender: AnyObject?) {
    transition.frontViewController = segue.destinationViewController
  }
```

##### 2. Your modal view controller must implement ElasticMenuTransitionDelegate
You can do this either by using storyboard or programatically. See example project.


## Todo

1. Support lower iOS versions(maybe by dropping UIKit Dynamics and use facebook Pop)
2. More settings to customize
3. Support navigation controller transition

## Author

Luke Zhao, me@lkzhao.com

## License

ElasticTransition is available under the MIT license. See the LICENSE file for more info.
