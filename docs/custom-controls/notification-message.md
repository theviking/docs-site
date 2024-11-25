---
layout: default
title: NotificationMessage
parent: Custom Controls
nav_order: 1
---

# NotificationMessage

## Reference
- Weave Web Site - [Notification Toasts](https://weave.autodesk.com/web/components/notifications-toasts) and [Notification Flyouts](https://weave.autodesk.com/web/components/notifications-flyout)
- Weave Figma States (WIP) - [Notification Toast](https://www.figma.com/file/ALLi7jxsFfwlJKiXkz7YAa/2.0-dev-ref?type=design&node-id=603%3A111889&mode=dev) and [Notification Flyout](https://www.figma.com/file/ALLi7jxsFfwlJKiXkz7YAa/2.0-dev-ref?type=design&node-id=603%3A111847&mode=dev)
- Weave MUI Storybook - [Notification](https://pages.git.autodesk.com/design-system/weave-mui/?path=/story/components-notification-notifications-flyout--default-story)

## Properties

|**Name**|**Type**|**Default**||
|:-------------|:-------------|:-------------|:-------------|
|Variant|enum|Simple| Simple / Icon |
|Status|enum|None| None / Info / Success / Warning / Error |
|Title|string|null||
|Message|string|null||
|LinkText|string|null||
|LinkAddress|Uri|null||
|TimeStampText|string|null|**TODO** - needs to be updated to accept a date and provide the time since that date|
|Closable|bool|null|Setting it to true shows the close button|
|CloseButtonToolTip|string|null||

## Notes
This is a custom control.

It is intended that the `NotificationMessage` will be hosted within the `NotificationToast` or `NotificationFlyout`.