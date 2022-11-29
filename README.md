# PHP WS NOTE

## Format ThumbImage

```php
{{UserInterfaceHelper::formatThumbMagazine($newsContent->Avatar3,null,1)}}

{{UserInterfaceHelper::formatThumbZoom($categoryInfo->Logo,300,188)}}

$value->AvatarVertical = !empty($value->Avatar2) ? UserInterfaceHelper::formatThumbZoom($value->Avatar2 ,$imgW, $imgH) : '';

$value->AvatarSquare = !empty($value->Avatar5) ? UserInterfaceHelper::formatThumbZoom($value->Avatar5,$imgW, $imgH) : '';
```

## Connect Info

#### 1. SVN

huuduc1/Kldowl90298892919!@392334

#### 2. VPN

ducvuhuu@channelvn.net / MSKF@jg9837jNSJF

#### 3. FTP

- 10.5.24.16@net5 SF34dfdf@@dghsd434
- FTPS Config :

```config
{
  "name": "PHP BETA",
  "host": "10.5.24.16",
  "protocol": "ftp",
  "port": 21,
  "username": "net5",
  "password": "SF34dfdf@@dghsd434",
  "remotePath": "/home/net5/hosting_php/",
  "uploadOnSave": true,
  "useTempFile": false,
  "openSsh": false
}
```

## Php js tool cd link

Add Extension to Browser:

- [Chrome](https://chrome.google.com/webstore/detail/run-javascript/lmilalhkkdhfieeienjbiicclobibjao)
- [Firefox](https://addons.mozilla.org/en-US/firefox/addon/javascript/)

Copy script to your extension to run:

- [Get Script](http://cdn.hevivu.cyou/cd-php-tool.js)

## Date format

{{date('H:i , d/m/Y',strtotime($item->CreatedDate))}}

## Check trùng bài

- Add class name

```html
<div class=".list__main_check .box-category-item">
  <div data-id="{{ $item->NewsId ?? '' }}"></div>
</div>
```

## Artisan command Modules

- Make Component

```Command
php artisan module:make-component Home/HighLight Mobile
```

[Read More](https://nwidart.com/laravel-modules/v6/advanced-tools/artisan-commands)

## View more loading

```html
<div class="box-stream-item box-stream-item-load"></div>

<div class=" box-stream-load fb-loading-wrapper" style="display: none">
  <div class="fblw-timeline-item">
    <div class="fblwti-animated">
      <div class="fblwtia-mask fblwtia-title-line fblwtia-title-mask-0"></div>
      <div class="fblwtia-mask fblwtia-sepline-sapo fblwtia-sapo-line-0"></div>
      <div
        class="fblwtia-mask fblwtia-sepline-sapo fblwtia-sepline-sapo-0"
      ></div>
      <div class="fblwtia-mask fblwtia-title-line fblwtia-title-mask-1"></div>
      <div class="fblwtia-mask fblwtia-sepline-sapo fblwtia-sapo-line-1"></div>
      <div
        class="fblwtia-mask fblwtia-sepline-sapo fblwtia-sepline-sapo-1"
      ></div>
      <div class="fblwtia-mask fblwtia-front-mask fblwtia-front-mask-2"></div>
      <div class="fblwtia-mask fblwtia-sapo-line fblwtia-sapo-line-2"></div>
      <div
        class="fblwtia-mask fblwtia-sepline-sapo fblwtia-sepline-sapo-2"
      ></div>
      <div class="fblwtia-mask fblwtia-front-mask fblwtia-front-mask-3"></div>
      <div class="fblwtia-mask fblwtia-sapo-line fblwtia-sapo-line-3"></div>
      <div
        class="fblwtia-mask fblwtia-sepline-sapo fblwtia-sepline-sapo-3"
      ></div>
      <div class="fblwtia-mask fblwtia-front-mask fblwtia-front-mask-4"></div>
      <div class="fblwtia-mask fblwtia-sapo-line fblwtia-sapo-line-4"></div>
      <div
        class="fblwtia-mask fblwtia-sepline-sapo fblwtia-sepline-sapo-4"
      ></div>
    </div>
  </div>
</div>

<a href="javascript:;" class="list__viewmor list__center" title="Xem thêm"
  >Xem thêm</a
>

<div class="configHidden">{!!$ZoneInfoClientScript!!}</div>
```

## Delay javascript function

```javascript
function delay(callback, ms) {
  var timer = 0;
  return function () {
    var context = this,
      args = arguments;
    clearTimeout(timer);
    timer = setTimeout(function () {
      callback.apply(context, args);
    }, ms || 0);
  };
}
```

## Clockwork

```Command
composer require itsgoingd/clockwork
```

## Gắn data-cd cho các box ngoài trang

- data-cd-key="{{key}}" =>gắn key cd theo vùng data đang lấy của box đó

- data-cd-top="{{number}}" =>number số lượng phần tủ lấy trong box

- data-cd-key-exclude="{{key}}" => "check trùng với box đang hiển thị}"

- data-cd-skip="{{number}}" =>số data skip

- data-cd-key,data-cd-top mặc định gắn còn lại gắn tùy trường hợp box

```php
data-cd-key="{{ $cdkey??'' }}"
data-cd-top="{{ $cdtop??'' }}"
data-cd-key-exclude="$keyexclude ?? '' }}"
data-cd-skip="{{ skip??'' }}"
```

```html
<x-slot name="cdkey"></x-slot>
<x-slot name="cdtop"></x-slot>
<x-slot name="keyexclude"></x-slot>
<x-slot name="skip"></x-slot>
```

```php
"{{ env('SITE_ID')}}newsinzone:zone{{ $NoticeInfo->Id??:'' }}"
```

## Check avartar gif

```blade.php
@if (strpos($item->ThumbImage, '.gif') !== false)
  <img loading="lazy" class="img160x100 lazy"
    data-original="{{ $item->ThumbImage }}"
    src="{{ $item->ThumbImage }}"
    alt="{{ $item->Title }}" />
@else
  <img loading="lazy"
    src="{{ $item->ThumbImage }}"
    class="img160x100" alt="{{ $item->Title }}" />
@endif
```

## Lọc keyword tìm kiếm

```php
$keywords = preg_replace('/(&#.\*)/', '', $keywords);
```

## Active menu script

```javascript
$.ajax({
  type: "GET",
  url: "ajax-list-subzone-news.htm",
  success: function (response) {
    response = JSON.parse(response);
    var html = "";
    $.each(response, function (index, item) {
      var subzone = "";
      var more = "";
      if (item["SubZone"]) {
        $.each(item["SubZone"], function (k, i) {
          subzone += `<a href="${i["ZoneUrl"]}" class="item" title="${i["Name"]}">${i["Name"]}</a>`;
        });
        if (item["SubZone"].length > 4) {
          more = `<a href="javascript:;" class="view-more" title="xem thêm">xem thêm</a>`;
        }
      }
      html += `<div class="box"><a href="${item["ZoneUrl"]}" class="title" title="${item["Name"]}">${item["Name"]}</a><div class="list">${subzone}</div>${more}</div>`;
      $(".header__mm-cate").html(html);
    });
  },
});
```
