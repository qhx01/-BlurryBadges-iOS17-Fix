# BlurryBadges iOS 17 Fix for RootHide

A compatibility fix for **PoomSmart's BlurryBadges** on **iOS 17** with **RootHide**.

This project keeps the original BlurryBadges behavior while fixing a SpringBoard crash that could occur when notification badges were updated.

## Problem

On iOS 17, BlurryBadges could crash SpringBoard during badge updates.

The crash path pointed to badge mask rendering inside `BackdropBadge.dylib`, specifically around:

```objc
UIGraphicsBeginImageContextWithOptions(...)
