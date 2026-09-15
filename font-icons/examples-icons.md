---
title: Examples Icons
page_title: .NET MAUI Font Icons - Examples Icons
description: Review the examples icons like filtering, sorting, gallery, avatar and more used in the Telerik UI for .NET MAUI components and examples.
slug: telerik-examples-icons
position: 1
previous_url: /font-icons/controls-icons
---

# Telerik UI for .NET MAUI Examples Icons

You can choose any of the available Telerik font icons: 

<main>
    <div class="icons-grid" id="grid"></div>
</main>

<div class="toast" id="toast">Copied!</div>

>important You need to set the Telerik example font icon code on the concrete property to visualize the icon. 

## Examples

This example shows how to add the font icons code to a Label. For this case you need to add the icon code to the `Label.Text` property and set the `FontFamily`:

```XAML
<Label Text="&#xe800;" FontFamily="TelerikFontExamples"/>
```
```C#
var label = new Label
{
    Text = "\ue800",
    FontFamily = "TelerikFontExamples"
};
```

>tip The `FontFamily` name is the name of the font registered in the `MauiProgram.cs` file.

## See Also

- [Icons Overview]({%slug telerik-font-icons%})


<style>
    :root {
        --bg: #f3f4f6;
        --surface: #ffffff;
        --surface-hover: #fbfdff;
        --border: #d9dee7;
        --border-strong: #cfd6e2;
        --text: #111827;
        --text-muted: #6b7280;
        --label: #7b8495;
        --accent: #2563eb;
        --accent-soft: rgba(37, 99, 235, 0.08);
        --success: #159957;
        --warning: #d97706;
        --radius-card: 14px;
        --radius-inner: 8px;
        --shadow: 0 8px 24px rgba(17, 24, 39, 0.06);
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
        font-family: "Inter", "Segoe UI", system-ui, -apple-system, sans-serif;
        background: var(--bg);
        color: var(--text);
        line-height: 1.45;
        min-height: 100vh;
    }

    main {
        max-width: 1700px;
        margin: 0 auto;
        padding: 1rem 1rem 2rem;
    }

    .icons-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(175px, 1fr));
        gap: 0.8rem;
        align-items: stretch;
    }

    .icon-card {
        background: var(--surface);
        border: 1px solid var(--border);
        border-radius: var(--radius-card);
        padding: 0.8rem 0.72rem 0.72rem;
        box-shadow: 0 1px 1px rgba(17, 24, 39, 0.02);
        transition: transform 0.15s ease, border-color 0.15s ease, box-shadow 0.15s ease;
        display: flex;
        flex-direction: column;
        gap: 0.48rem;
        min-width: 0;
    }

    .icon-card:hover {
        transform: translateY(-1px);
        border-color: var(--border-strong);
        box-shadow: var(--shadow);
    }

    .card-head {
        position: relative;
        min-height: 84px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 0.48rem;
        text-align: center;
        padding: 0.2rem 0.25rem 0.15rem;
    }

    .icon-preview {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        min-width: 28px;
        min-height: 28px;
        font-size: 1.55rem;
        line-height: 1;
        color: var(--accent);
        font-weight: 500;
    }

    .icon-name {
        font-size: 0.9rem;
        font-weight: 600;
        letter-spacing: -0.01em;
        color: var(--text);
        line-height: 1.2;
        overflow: hidden;
        display: -webkit-box;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
        min-height: 2.15em;
    }

    .source-warning {
        position: absolute;
        top: 0;
        right: 0;
        width: 8px;
        height: 8px;
        border-radius: 50%;
        background: var(--warning);
    }

    .code-row {
        display: flex;
        flex-direction: column;
        gap: 0.35rem;
    }

    .code-item {
        display: flex;
        align-items: center;
        gap: 0.4rem;
        min-height: 30px;
        border: 1px solid #e5e9f0;
        border-radius: var(--radius-inner);
        background: #f8fafc;
        padding: 0.34rem 0.38rem 0.34rem 0.5rem;
        min-width: 0;
        font-family: "JetBrains Mono", "Fira Code", "Consolas", monospace;
        font-size: 0.72rem;
    }

    .code-label {
        color: var(--label);
        font-size: 0.66rem;
        letter-spacing: 0.04em;
        text-transform: uppercase;
        flex: 0 0 auto;
        font-family: "Inter", "Segoe UI", system-ui, sans-serif;
        font-weight: 600;
    }

    .code-value {
        flex: 1;
        min-width: 0;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
        color: #234fb1;
    }

    .copy-btn {
        width: 22px;
        height: 22px;
        border: none;
        background: transparent;
        color: #8a94a6;
        border-radius: 6px;
        display: inline-flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        flex: 0 0 22px;
        transition: background 0.15s, color 0.15s;
    }

    .copy-btn:hover {
        color: var(--accent);
        background: var(--accent-soft);
    }

    .copy-btn.copied { color: var(--success); }
    .copy-btn svg { width: 14px; height: 14px; }

    .empty {
        grid-column: 1 / -1;
        text-align: center;
        padding: 3rem 1rem;
        color: var(--text-muted);
    }

    .empty svg { width: 42px; height: 42px; margin-bottom: 0.8rem; opacity: 0.45; }

    .toast {
        position: fixed;
        left: 50%;
        bottom: 1rem;
        transform: translateX(-50%) translateY(70px);
        opacity: 0;
        transition: transform 0.22s ease, opacity 0.22s ease;
        background: #1f2937;
        color: #fff;
        border-radius: 999px;
        padding: 0.55rem 0.9rem;
        font-size: 0.8rem;
        box-shadow: var(--shadow);
        pointer-events: none;
        z-index: 200;
    }

    .toast.show {
        transform: translateX(-50%) translateY(0);
        opacity: 1;
    }

    @media (min-width: 1680px) {
        .icons-grid { grid-template-columns: repeat(auto-fill, minmax(170px, 1fr)); }
    }

    @media (max-width: 900px) {
        .icons-grid { grid-template-columns: repeat(auto-fill, minmax(165px, 1fr)); }
    }

    @media (max-width: 640px) {
        .icons-grid { grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 0.6rem; }
        .icon-card { padding: 0.75rem 0.6rem 0.6rem; }
        .card-head { min-height: 78px; }
        .icon-preview { font-size: 1.4rem; }
        .icon-name { font-size: 0.82rem; }
        .code-item { font-size: 0.68rem; }
        .code-label { font-size: 0.62rem; }
    }

    @media (max-width: 420px) {
        .icons-grid { grid-template-columns: 1fr; }
    }
</style>

<script>
    const icons = [
        { name: "sort descent", xaml: "&#xe800;", code: "\\ue800", glyph: "images/sort-descent.png" },
        { name: "star-empty", xaml: "&#xe801;", code: "\\ue801", glyph: "images/star-empty.png" },
        { name: "filter", xaml: "&#xe802;", code: "\\ue802", glyph: "images/filter.png" },
        { name: "sort ascent", xaml: "&#xe803;", code: "\\ue803", glyph: "images/sort-ascent.png" },
        { name: "group", xaml: "&#xe804;", code: "\\ue804", glyph: "images/group.png" },
        { name: "star", xaml: "&#xe805;", code: "\\ue805", glyph: "images/star.png" },
        { name: "right-dir", xaml: "&#xe806;", code: "\\ue806", glyph: "images/right-dir.png" },
        { name: "dots vert", xaml: "&#xe807;", code: "\\ue807", glyph: "images/dots-vert.png" },
        { name: "menu", xaml: "&#xf008;", code: "\\uf008", glyph: "images/menu.png" },
        { name: "check", xaml: "&#xe876;", code: "\\ue876", glyph: "images/check.png" },
        { name: "cancel", xaml: "&#xe877;", code: "\\ue877", glyph: "images/cancel.png" },
        { name: "dot", xaml: "&#xe80b;", code: "\\ue80b", glyph: "images/dot.png" },
        { name: "dot-3", xaml: "&#xe80c;", code: "\\ue80c", glyph: "images/dot-3.png" },
        { name: "down-dir", xaml: "&#xe80d;", code: "\\ue80d", glyph: "images/down-dir.png" },
        { name: "chevron left", xaml: "&#xe80e;", code: "\\ue80e", glyph: "images/chevron-left.png" },
        { name: "configure", xaml: "&#xe80f;", code: "\\ue80f", glyph: "images/configure.png" },
        { name: "search", xaml: "&#xe810;", code: "\\ue810", glyph: "images/search.png" },
        { name: "up-dir", xaml: "&#xe811;", code: "\\ue811", glyph: "images/up-dir.png" },
        { name: "pattern", xaml: "&#xe812;", code: "\\ue812", glyph: "images/pattern.png" },
        { name: "add", xaml: "&#xe813;", code: "\\ue813", glyph: "images/add.png" },
        { name: "right-dir-outlines", xaml: "&#xe814;", code: "\\ue814", glyph: "images/right-dir-outlines.png" },
        { name: "info", xaml: "&#xe815;", code: "\\ue815", glyph: "images/info.png" },
        { name: "down-dir-outlines", xaml: "&#xe816;", code: "\\ue816", glyph: "images/down-dir-outlines.png" },
        { name: "bin-solid", xaml: "&#xe817;", code: "\\ue817", glyph: "images/bin-solid.png" },
        { name: "edit", xaml: "&#xe818;", code: "\\ue818", glyph: "images/edit.png" },
        { name: "copy", xaml: "&#xe819;", code: "\\ue819", glyph: "images/copy.png" },
        { name: "arrow-up", xaml: "&#xe81a;", code: "\\ue81a", glyph: "images/arrow-up.png" },
        { name: "airplane", xaml: "&#xe81c;", code: "\\ue81c", glyph: "images/airplane.png" },
        { name: "pdf", xaml: "&#xe81d;", code: "\\ue81d", glyph: "images/pdf.png" },
        { name: "encoding", xaml: "&#xe81e;", code: "\\ue81e", glyph: "images/encoding.png" },
        { name: "length", xaml: "&#xe81f;", code: "\\ue81f", glyph: "images/length.png" },
        { name: "arrow-right", xaml: "&#xe820;", code: "\\ue820", glyph: "images/arrow-right.png" },
        { name: "contacts", xaml: "&#xe821;", code: "\\ue821", glyph: "images/contacts.png" },
        { name: "cog-outlines", xaml: "&#xe822;", code: "\\ue822", glyph: "images/cog-outlines.png" },
        { name: "type", xaml: "&#xe823;", code: "\\ue823", glyph: "images/type.png" },
        { name: "location", xaml: "&#xe83d;", code: "\\ue83d", glyph: "images/location.png" },
        { name: "link", xaml: "&#xe83e;", code: "\\ue83e", glyph: "images/link.png" },
        { name: "archive", xaml: "&#xe826;", code: "\\ue826", glyph: "images/archive.png" },
        { name: "bin", xaml: "&#xe827;", code: "\\ue827", glyph: "images/bin.png" },
        { name: "draft", xaml: "&#xe828;", code: "\\ue828", glyph: "images/draft.png" },
        { name: "folder-open", xaml: "&#xe829;", code: "\\ue829", glyph: "images/folder-open.png" },
        { name: "folder", xaml: "&#xe82a;", code: "\\ue82a", glyph: "images/folder.png" },
        { name: "group", xaml: "&#xe82b;", code: "\\ue82b", glyph: "images/group.png" },
        { name: "item", xaml: "&#xe82c;", code: "\\ue82c", glyph: "images/item.png" },
        { name: "sent", xaml: "&#xe82d;", code: "\\ue82d", glyph: "images/sent.png" },
        { name: "spam", xaml: "&#xe82e;", code: "\\ue82e", glyph: "images/spam.png" },
        { name: "warning", xaml: "&#xe82f;", code: "\\ue82f", glyph: "images/warning.png" },
        { name: "lock", xaml: "&#xe830;", code: "\\ue830", glyph: "images/lock.png" },
        { name: "thickness", xaml: "&#xe831;", code: "\\ue831", glyph: "images/thickness.png" },
        { name: "car", xaml: "&#xe832;", code: "\\ue832", glyph: "images/car.png" },
        { name: "shopping-bag", xaml: "&#xe833;", code: "\\ue833", glyph: "images/shopping-bag.png" },
        { name: "coffee-cup", xaml: "&#xe834;", code: "\\ue834", glyph: "images/coffee-cup.png" },
        { name: "get-money", xaml: "&#xe835;", code: "\\ue835", glyph: "images/get-money.png" },
        { name: "shopping-user", xaml: "&#xe836;", code: "\\ue836", glyph: "images/shopping-user.png" },
        { name: "group users", xaml: "&#xe837;", code: "\\ue837", glyph: "images/group-users.png" },
        { name: "dashboard", xaml: "&#xe838;", code: "\\ue838", glyph: "images/dashboard.png" },
        { name: "first", xaml: "&#xe839;", code: "\\ue839", glyph: "images/first.png" },
        { name: "cake", xaml: "&#xe83a;", code: "\\ue83a", glyph: "images/cake.png" },
        { name: "chat", xaml: "&#xe83b;", code: "\\ue83b", glyph: "images/chat.png" },
        { name: "book", xaml: "&#xe83c;", code: "\\ue83c", glyph: "images/book2.png" },
        { name: "assets", xaml: "&#xe846;", code: "\\ue846", glyph: "images/assets2.png" },
        { name: "book", xaml: "&#xe847;", code: "\\ue847", glyph: "images/book2.png" },
        { name: "cancel", xaml: "&#xe851;", code: "\\ue851", glyph: "images/cancel2.png" },
        { name: "design", xaml: "&#xe848;", code: "\\ue848", glyph: "images/design.png" },
        { name: "graphics", xaml: "&#xe849;", code: "\\ue849", glyph: "images/graphics.png" },
        { name: "picture", xaml: "&#xe852;", code: "\\ue852", glyph: "images/picture.png" },
        { name: "font-size", xaml: "&#xe84b;", code: "\\ue84b", glyph: "images/font-size.png" },
        { name: "template", xaml: "&#xe84c;", code: "\\ue84c", glyph: "images/template.png" },
        { name: "wireframes", xaml: "&#xe84d;", code: "\\ue84d", glyph: "images/wireframes.png" },
        { name: "distance", xaml: "&#xe84e;", code: "\\ue84e", glyph: "images/distance.png" },
        { name: "stopwatch", xaml: "&#xe84f;", code: "\\ue84f", glyph: "images/stopwatch.png" },
        { name: "play", xaml: "&#xe850;", code: "\\ue850", glyph: "images/play.png" },
        { name: "code", xaml: "&#xe854;", code: "\\ue854", glyph: "images/code.png" },
        { name: "analysis", xaml: "&#xe855;", code: "\\ue855", glyph: "images/analysis.png" },
        { name: "network", xaml: "&#xe856;", code: "\\ue856", glyph: "images/network.png" },
        { name: "network", xaml: "&#xe857;", code: "\\ue857", glyph: "images/network2.png" },
        { name: "bar-chart", xaml: "&#xe858;", code: "\\ue858", glyph: "images/bar-chart.png" },
        { name: "sap", xaml: "&#xe859;", code: "\\ue859", glyph: "images/sap.png" },
        { name: "dba", xaml: "&#xe85a;", code: "\\ue85a", glyph: "images/dba.png" },
        { name: "home", xaml: "&#xe85b;", code: "\\ue85b", glyph: "images/home.png" },
        { name: "temperature", xaml: "&#xe85c;", code: "\\ue85c", glyph: "images/temperature.png" },
        { name: "phone", xaml: "&#xe85d;", code: "\\ue85d", glyph: "images/phone.png" },
        { name: "electricity", xaml: "&#xe85e;", code: "\\ue85e", glyph: "images/electricity.png" },
        { name: "wifi", xaml: "&#xe85f;", code: "\\ue85f", glyph: "images/wifi.png" },
        { name: "distance-horizontal", xaml: "&#xe860;", code: "\\ue860", glyph: "images/distance-horizontal.png" },
        { name: "calendar dayview", xaml: "&#xe861;", code: "\\ue861", glyph: "images/calendar-dayview.png" },
        { name: "calendar multiday", xaml: "&#xe862;", code: "\\ue862", glyph: "images/calendar-multiday.png" },
        { name: "calendar week", xaml: "&#xe863;", code: "\\ue863", glyph: "images/calendar-week.png" },
        { name: "calendar month", xaml: "&#xe864;", code: "\\ue864", glyph: "images/calendar-month.png" },
        { name: "calendar year", xaml: "&#xe865;", code: "\\ue865", glyph: "images/calendar-year.png" },
        { name: "calendar selection single", xaml: "&#xe866;", code: "\\ue866", glyph: "images/calendar-selection-single.png" },
        { name: "calendar selection multiple", xaml: "&#xe867;", code: "\\ue867", glyph: "images/calendar-selection-multiple.png" },
        { name: "calendar selection range", xaml: "&#xe868;", code: "\\ue868", glyph: "images/calendar-selection-range.png" },
        { name: "gallery", xaml: "&#xe869;", code: "\\ue869", glyph: "images/gallery.png" },
        { name: "camera", xaml: "&#xe86a;", code: "\\ue86a", glyph: "images/camera.png" },
        { name: "crop free", xaml: "&#xe86b;", code: "\\ue86b", glyph: "images/crop-free.png" },
        { name: "crop original", xaml: "&#xe86c;", code: "\\ue86c", glyph: "images/crop-original.png" },
        { name: "crop rect", xaml: "&#xe86d;", code: "\\ue86d", glyph: "images/crop-rect.png" },
        { name: "crop circular", xaml: "&#xe86e;", code: "\\ue86e", glyph: "images/crop-circular.png" },
        { name: "badge", xaml: "&#xe86f;", code: "\\ue86f", glyph: "images/badge.png" },
        { name: "notes", xaml: "&#xe870;", code: "\\ue870", glyph: "images/notes.png" },
        { name: "time", xaml: "&#xe871;", code: "\\ue871", glyph: "images/time.png" },
        { name: "calendar agenda", xaml: "&#xe872;", code: "\\ue872", glyph: "images/calendar-agenda.png" },
        { name: "arrows", xaml: "&#xe873;", code: "\\ue873", glyph: "images/arrows.png" },
        { name: "video-camera", xaml: "&#xe87;", code: "\\ue874", glyph: "images/video-camera.png" },
        { name: "check", xaml: "&#xe878;", code: "\\ue878", glyph: "images/time.png" },
        { name: "cancel", xaml: "&#xe887;", code: "\\ue887", glyph: "images/phone.png" },
        { name: "text", xaml: "&#xe853;", code: "\\ue853", glyph: "images/text.png" },
        { name: "arrow-down", xaml: "&#xe879;", code: "\\ue879", glyph: "images/arrow-down.png" },
        { name: "flag", xaml: "&#xe87a;", code: "\\ue87a", glyph: "images/flag.png" },
        { name: "save", xaml: "&#xe87b;", code: "\\ue87b", glyph: "images/save.png" },
        { name: "share", xaml: "&#xe87c;", code: "\\ue87c", glyph: "images/share.png" },
        { name: "menu-custom", xaml: "&#xe87d;", code: "\\ue87d", glyph: "images/menu-custom.png" },
        { name: "heart-filled", xaml: "&#xe87e;", code: "\\ue87e", glyph: "images/heart-filled.png" },
        { name: "heart-empty", xaml: "&#xe87f;", code: "\\ue87f", glyph: "images/heart-empty.png" },
        { name: "reorder", xaml: "&#xe881;", code: "\\ue881", glyph: "images/reorder.png" },
        { name: "arrow-box-left", xaml: "&#xe882;", code: "\\ue882", glyph: "images/arrow-box-left.png" },
        { name: "arrow-box-right", xaml: "&#xe883;", code: "\\ue883", glyph: "images/arrow-box-right.png" },
        { name: "bell", xaml: "&#xe88a;", code: "\\ue88a", glyph: "images/bell.png" },
        { name: "chat", xaml: "&#xe88b;", code: "\\ue88b", glyph: "images/chat.png" },
        { name: "phone", xaml: "&#xe904;", code: "\\ue887", glyph: "images/phone.png" },
        { name: "unpin", xaml: "&#xe88e;", code: "\\ue88e", glyph: "images/unpin.png" },
        { name: "pin", xaml: "&#xe88f;", code: "\\ue88f", glyph: "images/pin.png" },
        { name: "excel", xaml: "&#xe896;", code: "\\ue896", glyph: "images/excel.png" },
        { name: "powerpoint", xaml: "&#xe897;", code: "\\ue897", glyph: "images/powerpoint.png" },
        { name: "word", xaml: "&#xe898;", code: "\\ue898", glyph: "images/word.png" },
        { name: "pdf", xaml: "&#xe899;", code: "\\ue899", glyph: "images/pdf.png" },
        { name: "last", xaml: "&#xe89a;", code: "\\ue89a", glyph: "images/last.png" },
        { name: "expand", xaml: "&#xe89b;", code: "\\ue89b", glyph: "images/expand.png" },
        { name: "expand 2", xaml: "&#xe89c;", code: "\\ue89c", glyph: "images/expand2.png" },
        { name: "paint bucket", xaml: "&#xe89d;", code: "\\ue89d", glyph: "images/paint-bucket.png" },
        { name: "mail", xaml: "&#xe89e;", code: "\\ue89e", glyph: "images/mail.png" },
        { name: "promotion", xaml: "&#xe89f;", code: "\\ue89f", glyph: "images/promotion.png" },
        { name: "scheduled", xaml: "&#xe8a0;", code: "\\ue8a0", glyph: "images/scheduled.png" },
        { name: "label", xaml: "&#xe8a1;", code: "\\ue8a1", glyph: "images/label.png" },
        { name: "drawer", xaml: "&#xe8a2;", code: "\\ue8a2", glyph: "images/drawer.png" },
        { name: "social", xaml: "&#xe8a3;", code: "\\ue8a3", glyph: "images/social.png" },
        { name: "shipping", xaml: "&#xe8a6;", code: "\\ue8a6", glyph: "images/shipping.png" },
        { name: "products", xaml: "&#xe8a7;", code: "\\ue8a7", glyph: "images/products.png" },
        { name: "customer", xaml: "&#xe8a8;", code: "\\ue8a8", glyph: "images/customer.png" },
        { name: "export", xaml: "&#xe8a9;", code: "\\ue8a9", glyph: "images/export.png" },
        { name: "info-outlines", xaml: "&#xe8ac;", code: "\\ue8ac", glyph: "images/info-outlines.png" },
        { name: "contract", xaml: "&#xe8dd;", code: "\\ue8dd", glyph: "images/contract.png" },
        { name: "enlarge", xaml: "&#xe8de;", code: "\\ue8de", glyph: "images/enlarge.png" },
        { name: "translate", xaml: "&#xe8df;", code: "\\ue8df", glyph: "images/translate.png" },
        { name: "emoji", xaml: "&#xe900;", code: "\\ue900", glyph: "images/emoji.png" },
        { name: "brightness", xaml: "&#xe901;", code: "\\ue901", glyph: "images/brightness.png" },
        { name: "flip-vertical", xaml: "&#xe902;", code: "\\ue902", glyph: "images/flip-vertical.png" },
        { name: "flip-horizontal", xaml: "&#xe903;", code: "\\ue903", glyph: "images/flip-horizontal.png" },
        { name: "rotate-cw", xaml: "&#xe904;", code: "\\ue904", glyph: "images/rotate-cw.png" },
        { name: "rotate-ccw", xaml: "&#xe905;", code: "\\ue905", glyph: "images/rotate-ccw.png" },
        { name: "crop", xaml: "&#xe906;", code: "\\ue906", glyph: "images/crop.png" },
        { name: "hue", xaml: "&#xe907;", code: "\\ue907", glyph: "images/hue.png" },
        { name: "link-external", xaml: "&#xf08e;", code: "\\uf08e", glyph: "images/link-external.png" },
        { name: "plus-squared", xaml: "&#xf0fe;", code: "\\uf0fe", glyph: "images/plus-squared.png" },
        { name: "angle-left", xaml: "&#xf104;", code: "\\uf104", glyph: "images/angle-left.png" },
        { name: "angle-right", xaml: "&#xf105;", code: "\\uf105", glyph: "images/angle-right.png" },
        { name: "angle-up", xaml: "&#xf106;", code: "\\uf106", glyph: "images/angle-up.png" },
        { name: "angle-down", xaml: "&#xf107;", code: "\\uf107", glyph: "images/angle-down.png" },
        { name: "spinner", xaml: "&#xf110;", code: "\\uf110", glyph: "images/spinner.png" },
        { name: "arrow-circled-left", xaml: "&#xf137;", code: "\\uf137", glyph: "images/arrow-circled-left.png" },
        { name: "arrow-circled-right", xaml: "&#xf138;", code: "\\uf138", glyph: "images/arrow-circled-right.png" },
        { name: "minus-squared", xaml: "&#xf146;", code: "\\uf146", glyph: "images/minus-squared.png" },
        { name: "minus-squared-alt", xaml: "&#xf147;", code: "\\uf147", glyph: "images/minus-squared-alt.png" },
        { name: "plus-squared-alt", xaml: "&#xf196;", code: "\\uf196", glyph: "images/plus-squared-alt.png" },
        ];

    const grid = document.getElementById("grid");
    const toast = document.getElementById("toast");

    function showToast(msg = "Copied!") {
      toast.textContent = msg;
      toast.classList.add("show");
      setTimeout(() => toast.classList.remove("show"), 1800);
    }

    function escapeHtml(value) {
      return String(value)
        .replace(/&/g, "&amp;")
        .replace(/</g, "&lt;")
        .replace(/>/g, "&gt;")
        .replace(/"/g, "&quot;")
        .replace(/'/g, "&#039;");
    }

    function copyText(text, btn) {
      navigator.clipboard.writeText(text).then(() => {
        btn.classList.add("copied");
        showToast();
        setTimeout(() => btn.classList.remove("copied"), 1500);
      });
    }

    function render(list) {
      if (!list.length) {
        grid.innerHTML = `
          <div class="empty">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><circle cx="11" cy="11" r="8"/><path d="m21 21-4.3-4.3"/></svg>
            <p>No icons found</p>
          </div>`;
        return;
      }

      grid.innerHTML = list.map(icon => `
        <article class="icon-card" data-name="${escapeHtml(icon.name)}">
          <div class="card-head">
            ${icon.sourceIssue ? '<span class="source-warning" title="Official Telerik docs currently contain inconsistent XAML/Code values for this row"></span>' : ''}
            <div class="icon-preview" title="${escapeHtml(icon.name)}">${escapeHtml(icon.glyph)}</div>
            <div class="icon-name">${escapeHtml(icon.name)}</div>
          </div>
          <div class="code-row">
            <div class="code-item">
              <span class="code-label">XAML</span>
              <span class="code-value">${escapeHtml(icon.xaml)}</span>
              <button class="copy-btn" title="Copy XAML" data-copy="${escapeHtml(icon.xaml)}" onclick="copyText(this.dataset.copy, this)">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="9" y="9" width="13" height="13" rx="2"/><path d="M5 15H4a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2h9a2 2 0 0 1 2 2v1"/></svg>
              </button>
            </div>
            <div class="code-item">
              <span class="code-label">Code</span>
              <span class="code-value">${escapeHtml(icon.code)}</span>
              <button class="copy-btn" title="Copy Code" data-copy="${escapeHtml(icon.code)}" onclick="copyText(this.dataset.copy, this)">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="9" y="9" width="13" height="13" rx="2"/><path d="M5 15H4a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2h9a2 2 0 0 1 2 2v1"/></svg>
              </button>
            </div>
          </div>
        </article>`).join("");
    }

    render(icons);
</script>