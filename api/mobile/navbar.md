---
title: kendo.mobile.ui.NavBar
slug: mobile-kendo.mobile.ui.navbar
tags: api,mobile
publish: true
---

# kendo.mobile.ui.NavBar

## Description



The Kendo mobile NavBar widget is used inside a mobile View or Layout Header element to display an application navigation bar.
The mobile NavBar may display the current view title in the center, and optionally some additional left and right aligned widgets (a back button, settings button, etc.).

### Getting Started

The Kendo mobile Application will automatically initialize the mobile NavBar for every element with `role` data attribute set to `navbar` present in the views/layouts markup.
Alternatively, it can be initialized using jQuery plugin syntax in the containing mobile View **init event handler**.

#### Initialize Kendo mobile NavBar based on role data attribute

    <div data-role="navbar">My View Title</div>

#### Initialize Kendo mobile NavBar using jQuery plugin syntax

    var navbar = $("#navbar").kendoMobileNavBar();

### Aligning Widgets Inside the NavBar

After initialization, the mobile NavBar positions its child elements based on the specified `align` data attribute (either `left` or `right`).
By default, elements without any align are centered.

#### Use the `align` data attribute to specify the elements position inside the NavBar

    <div data-role="navbar">
      <a data-role="backbutton" data-align="left">Back</a>
      My View Title
      <a data-role="button" data-align="right">About</a>
    </div>

### Automatically Update NavBar Title Based on Current View's Title

If an element with `role` data attribute set to `view-title` is present inside the mobile NavBar,
the Kendo mobile Application instance will update its text to the current View's title when changing views.
The View title is specified by setting the `title` data attribute of the View element. 

This feature is particularly useful if the mobile NavBar is inside a layout.

#### Use the `view-title` data attribute to auto-update the mobile NavBar title

    <div data-role="layout" data-id="foo">
      <div data-role="header">
          <div data-role="navbar">
             <span data-role="view-title">My View Title</span>
          </div>
      </div>
    </div>
    
    <div data-role="view" data-layout="foo" data-title="bar"> ... </div>
    <div data-role="view" data-layout="foo" data-title="baz"> ... </div>

### Customizing Mobile NavBar Appearance

The mobile NavBar background color can be customized by setting its background-color CSS property either inline or using a CSS selector with specificity of 20+.
Different platforms can be styled separately with their respective root classes. 

#### Green Kendo mobile NavBar

    <div data-role="navbar" style="background-color: green">My View Title</div>

#### Green Kendo mobile NavBar in iOS and a red one in Android

    <style>
        .km-ios .checkout { background-color: green; }
        .km-android .checkout { background-color: red; }
    </style>
    <div data-role="navbar" class="checkout">My View Title</div>

## Methods

### title

Update the title element text. The title element is specified by setting the `role` data attribute to `view-title`.

#### Example

    <div data-role="navbar" id="foo">
        <span data-role="view-title"></span>
    </div>
    
    <script>
      $("#foo").data("kendoMobileNavBar").title("Foo");
    </script>

#### Parameters

##### value `String`

The text of title