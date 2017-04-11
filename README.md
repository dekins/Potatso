# Potatso ![GPLv3 License](https://img.shields.io/badge/License-GPLv3-blue.svg)

## Important

Please read [this](https://github.com/haxpor/Potatso/blob/master/ADHERE_LICENSE.md) first before you do anything with this project.  
In short, you need to respect to license of the project. You cannot copy the source code and publish to App Store.

---

## What is it?

Potatso is an iOS client that implements custom proxies with the leverage of Network Extension framework introduced by Apple since iOS 9.

Currently, Potatso is compatible with following proxies:

- [Shadowsocks](https://shadowsocks.org)
- [ShadowsocksR](https://github.com/breakwa11/shadowsocks-rss)

[Subscribe Telegram Channel](https://telegram.me/potatso) to get updates of Potatso.  
[Join Telegram Group](https://telegram.me/joinchat/BT0c4z49OGNZXwl9VsO0uQ) to chat with users.

Original Author: [@icodesign](https://twitter.com/icodesign_me)  
Swift 3 Maintainer: [@haxpor](https://twitter.com/haxpor)

## Project Info

Potatso has in total 33 (2 as submodules dependencies as used as local file in Cocoapod) dependencies as following

* 28 Cocoapod dependencies
* 1 Carthage dependency
* 4 submodules dependencies

The project is tested with Xcode 8.2 (8C38) on iOS 10.2 (14C92) device with cocoapod version `1.1.1`+.

## Change log

You can take a look at [Change log](https://github.com/haxpor/Potatso/wiki/Change-log) for changes that has made for specific commit that has significant updates. Thus you can freely decide whether you want to rebuild Potatso to include such update or not.

## How to Build Project

Perform the following steps to be able to build the project.
Be warned that you **should not** call `pod update` as newer version of pod frameworks that Potatso depends on might break building process and there will be errors.

1. `git submodule update --init` to update git submodule
2. `pod install` to pull down dependencies into our project
3. `carthage update` to pull down dependencies into `Carthage/Checkouts` folder and build each one
4. Open `Potatso.xcworkspace` then Build and Run the project. Done.

## Build Notices

If you try to build for iOS 10.3, please try to use XCode Version 8.3 (8E162) onwards and only for release version.

## Code Notices

There're a couple of issues that needed to look at, but after testing, it does **not** affect the functionality of the app.

* In file `Potatso/Core/API.swift`, it's the following code focusing on line with comment that I can't figure it out yet how to migrate it to Swift 3 code.  

   ```swift
   var JSONToMap: AnyObject?
   if let keyPath = keyPath, keyPath.isEmpty == false {
       //JSONToMap = (result.value? as AnyObject).value(forKeyPath: keyPath)
       JSONToMap = nil
   } else {
       JSONToMap = result.value as AnyObject?
   }
   ```
* Potatso core code depends on version `1.7.0` of Eureka with manual migration to Swift 3. It's already done and linked to project. But you will see `observeValue()` function in `Eureka/Source/Rows/PostalAddressRow.swift` that has been commented for all of its function code due to Eureka's newer version `2.0.0-beta.1` doesn't include such file in the project anymore, but it still works with no problem. This note is meant to mark that there is going to be a lot of effort if we decide to depend on Eureka version `2.0.0-beta.1` as we need to change a lot of Potatso core code.
   
## How To Contribute

Clone the project, make some changes or add a new feature, then make a pull request.

## Acknowlegements

We use the following services or open-source libraries. So we'd like show them highest respect and thank for bringing those great projects:

### Services

- [Fabric](https://get.fabric.io/)
- [Reveal](http://revealapp.com/)
- [realm](https://realm.io/)
- [HelpShift](https://www.helpshift.com)

### Open-source Libraries

- [KissXML](https://github.com/robbiehanson/KissXML)
- [MMWormhole](https://github.com/mutualmobile/MMWormhole)
- [CocoaAsyncSocket](https://github.com/robbiehanson/CocoaAsyncSocket)
- [Cartography](https://github.com/robb/Cartography)
- [AsyncSwift](https://github.com/duemunk/Async)
- [Appirater](https://github.com/arashpayan/appirater)
- [Eureka](https://github.com/xmartlabs/Eureka)
- [MBProgressHUD](https://github.com/matej/MBProgressHUD)
- [CallbackURLKit](https://github.com/phimage/CallbackURLKit)
- [ISO8601DateFormatter](https://github.com/boredzo/iso-8601-date-formatter)
- [Alamofire](https://github.com/Alamofire/Alamofire)
- [ObjectMapper](https://github.com/Hearst-DD/ObjectMapper)
- [CocoaLumberjack](https://github.com/CocoaLumberjack/CocoaLumberjack)
- [AlamofireObjectMapper](https://github.com/tristanhimmelman/AlamofireObjectMapper)
- [YAML.framework](https://github.com/mirek/YAML.framework)
- [tun2socks-iOS](https://github.com/shadowsocks/tun2socks-iOS)
- [shadowsocks-libev](https://github.com/shadowsocks/shadowsocks-libev)
- [Antinat](http://antinat.sourceforge.net/)
- [Privoxy](https://www.privoxy.org/)

### Also we'd like to thank people that helped with the project

- [@Blankwonder](https://twitter.com/Blankwonder)
- [@龙七](#)
- [@haxpor](https://twitter.com/haxpor)
- TestFlight Users and [Telegram Group](https://telegram.me/joinchat/BT0c4z49OGNZXwl9VsO0uQ) users.

### Donate
- [@liqianyu](https://twitter.com/liqianyu)
- [@anonymous](#) x2

## Notice

Potatso 2 is in beta and likely to come out not too long in the future.  
You can wait to purchase Potatso 2 from App Store, or still use Potatso by building it and installing to your device from this project.

Please note that Potatso 2 will be closed-source as stated from original author's reason. Read more from [here](https://github.com/haxpor/Potatso/blob/master/ADHERE_LICENSE.md).

## Support Us

The development covers a lot of complicated work, costing not only money but also time.
These are the way to support

- [Download Potatso from Apple Store](https://itunes.apple.com/app/apple-store/id1070901416?pt=2305194&ct=potatso.github&mt=8). (**Recommended**) 
- Donate with Alipay to original author. (Account: **leewongstudio.com@gmail.com**)
- Donate to swift3 maintainer (WeChat: http://imgur.com/lsAao62, or PayPal: haxpor@gmail.com)

## License

**You cannot just copy the project, and publish to App Store.**  Please read [this](https://github.com/haxpor/Potatso/blob/master/ADHERE_LICENSE.md) first.

--

To be compatible with those libraries using GPL, we're distributing with GPLv3 license.

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see http://www.gnu.org/licenses/.


Potatso is an iOS client that implements custom proxies with the leverage of Network Extension framework introduced by Apple since iOS 9.

Currently, Potatso is compatible with following proxies:

Shadowsocks
ShadowsocksR
Subscribe Telegram Channel to get updates of Potatso.

Join Telegram Group to chat with users.

Author: icodesign

Project Info
Potatso has in total 31 dependencies as following

28 Cocoapod dependencies
1 Carthage dependency
2 submodules dependencies
The project is tested with Xcode 8.2 (8C38) on iOS 10.2 (14C92) device with cocoapod version 1.1.1.

Set up Guide - Code
Perform the following steps to be able to build the project. Be warned that you should not call pod update as newer version of pod frameworks that Potatso depends on might break building process and there will be errors.

git submodule update --init to update git submodule
pod install to pull down dependencies into our project
carthage update to pull down dependencies into Carthage/Checkouts folder and build each one
Open Xcode workspace project (Potatso.xcworkspace).
Click on Potatso project, then click on General tap.
Click on Potatso target at Targets section.
Change its Bundle Identifier to match with your desire domain name for example com.yourdomain.potatso.
For the following targets, you change io.wasin.potatso to match your domain name. This means if you see io.wasin.potatso.tunnel, you change it to com.yourdomain.potatso.tunnel.
PacketTunnel
TodayWidget
PotatsoLibrary
PacketProcessor
PotatsoModel
PotatsoBase
Follow the guide in Set up Guide - Apple Developer Website section.
Build and Run the project. Done.
Set up Guide - Apple Developer Website
Note that it's better to not allow Xcode to automatically manage your provisioning profile for the application included Potatso (main app), PacketTunnel (extension), and TodayWidget (extension). Most of the time, such provisioning profile won't generate on developer page, or point to generic one which makes it not working!.

So follow the following steps

Create 3 App IDs for Potatso, PacketTunnel, and TodayWidget on Apple Developer website. Make sure to name bundle id for each one matches bundle identifier you used when setting up with Xcode. In this case io.wasin.potatso, io.wasin.potatso.tunnel, and io.wasin.potatso.todaywidget respectively. Rename to be your domain name freely.

Potatso
Enable App Groups, Game Center, iCloud, In-App Purchase, Network Extensions, and Push Notifications.
PacketTunnel
Enable App Groups, Game Center, In-App Purchase, and Network Extensions.
TodayWidget
Enable App Groups, Game Center, In-App Purchase, and Network Extensions.
Create 3 corresponding provisioning profile for each created App ID on Apple Developer website.

Now go back to Xcode

Click on project -> click on General tap -> select Potatso target and uncheck Automatically manage signing -> select a proper provisioning profile in both Signing (Debug) and Signing (Release).

Do the same for PacketTunnel and TodayWidget target.

Code Notices
There're a couple of issues that needed to look at, but at tested, it doen not effect the functionality of the app.

In file Potatso/Core/API.swift, it's the following code focusing on line with comment that I can't figure it out yet how to migrate it to Swift 3 code.
   var JSONToMap: AnyObject?
   if let keyPath = keyPath, keyPath.isEmpty == false {
       //JSONToMap = (result.value? as AnyObject).value(forKeyPath: keyPath)
       JSONToMap = nil
   } else {
       JSONToMap = result.value as AnyObject?
   }
Potatso core code depends on version 1.7.0 of Eureka with manual migration to Swift 3. It's already done and linked to project. But you will see observeValue() function in Eureka/Source/Rows/PostalAddressRow.swift that has been commented for all of its function code due to Eureka's newer version 2.0.0-beta.1 doesn't include such file in the project anymore, but it still works with no problem. This note is meant to mark that there is going to be a lot of effort if we decide to depend on Eureka version 2.0.0-beta.1 as we need to change a lot of Potatso core code.
How To Contribute
Clone the project, make some changes or add a new feature, then make a pull request.

Support Us
The development covers a lot of complicated work, costing not only money but also time.

There're two ways you can support us:

Download Potatso from Apple Store. (Recommended)

Donate with Alipay. (Account: leewongstudio.com@gmail.com)

Acknowlegements
We use the following services or open-source libraries. So we'd like show them highest respect and thank for bringing those great projects:

Services:

Fabric
Reveal
realm
HelpShift
Open-source Libraries:

KissXML
MMWormhole
CocoaAsyncSocket
Cartography
AsyncSwift
Appirater
Eureka
MBProgressHUD
CallbackURLKit
ISO8601DateFormatter
Alamofire
ObjectMapper
CocoaLumberjack
AlamofireObjectMapper
YAML.framework
tun2socks-iOS
shadowsocks-libev
Antinat
Privoxy
Also we'd like to thank people that helped with the project:

@Blankwonder
@
@haxpor
or donated us:

@liqianyu
@anonymous x2
And also thank all TestFlight Users and Telegram Group Users.

Thanks again!

