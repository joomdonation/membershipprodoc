---
title: 'Fix PDF Fonts'
media_order: greek-fonts.zip
---

In some languages, there are special characters which could not be rendered properly in the PDF invoices, tickets.... using default font, and in these cases, you need to configure Events Booking to use different PDF font which works for your languages

1. Login to administrator area of your site
2. Access to this URL to download all available PDF fonts into your site **https://domain.com/administrator/index.php?option=com_osmembership&task=tool.download_and_set_font**
(replace **https://domain.com/administrator** with administrator URL of your site)
3. Go to **Membership Pro** -> **Configuration**, look at **PDF Settings** tab, choose from one of the available font for **PDF Font** config option until you find the font which works for your language

- Maybe you should try to choose from one of the following first **freesans**, **dejavuserif** or **Freeserif**. These UTF8 fonts should work for your language.
- If not, try to Google for the font for your language. Something like "TCPDF font for German language", "TCDPF font for Greek language". If you see some font, then choose it from the above config option.