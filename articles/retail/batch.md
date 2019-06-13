<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="batch.md" target-language="pl-PL">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-d915bc8" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>batch.e70006.4456fc3d5bc4547fa8211642b11ca6df455fa187.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>4456fc3d5bc4547fa8211642b11ca6df455fa187</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>aec1dcd44274e9b8d0770836598fde5533b7b569</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>06/03/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\batch.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Improved handling of batch-tracked items</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ulepszona obsługa towarów śledzonych w partii</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes the improvements that have been made to the handling of batches for batch-tracked items during the Retail statement posting process.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">W tym temacie opisano ulepszenia dotyczące obsługi partii (w zakresie towarów śledzonych w partii) podczas procesu księgowania zestawienia handlu detalicznego</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Improved handling of batch-tracked items</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Ulepszona obsługa towarów śledzonych w partii</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>In Microsoft Dynamics 365 for Retail Point of Sale (POS), batch numbers can't be captured for batch-tracked items at the time of sale.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">W punkcie sprzedaży (POS) rozwiązania Microsoft Dynamics 365 for Retail nie można w momencie sprzedaży przechwytywać numerów partii dla towarów śledzonych w partii.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>However, for specific configurations, when sales are posted in the headquarters through customer orders or statement posting, the Microsoft Dynamics system expects that valid batch numbers for batch-tracked items exist, and that they will be used during the invoicing process.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Jednak w przypadku określonych konfiguracji, gdy sprzedaż jest księgowana w centrali w ramach procesu księgowania zamówień odbiorcy lub zestawień, system Microsoft Dynamics oczekuje, że istnieją prawidłowe numery partii dla towarów śledzonych w partii oraz że będą one używane w procesie fakturowania.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>If valid batch numbers are available for products, the customer order invoicing process and the sales order invoicing process from statement posting use them.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Jeśli dla produktów są dostępne prawidłowe numery partii, będą one używane w procesie fakturowania zamówień odbiorcy oraz procesie fakturowania zamówień sprzedaży na podstawie księgowania zestawienia.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Otherwise, the customer order invoicing process can't post, and the POS user receives an error message.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">W przeciwnym razie nie będzie można wykonać księgowania w ramach procesu fakturowania zamówień odbiorcy, a użytkownik w punkcie sprzedaży zobaczy komunikat o błędzie.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Statement posting then goes into an error state.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Następnie proces księgowania zestawienia przejdzie do stanu błędu.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>This error state occurs even when negative inventory has been turned on for the products.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ten stan błędu występuje nawet wtedy, gdy dla produktów został włączony ujemny poziom zapasów.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Improvements that have been made in Microsoft Dynamics for Retail version 10.0.4 and later help guarantee that, when negative inventory is turned on for batch-tracked items, customer order invoicing and sales order invoicing through statement posting aren't blocked for those items if the inventory is 0 (zero) or a batch number isn't available.</source><target logoport:matchpercent="0" state="translated">Ulepszenia wprowadzone w rozwiązaniu Microsoft Dynamics for Retail w wersji 10.0.4 i nowszych umożliwiają zagwarantowanie, że w sytuacji, gdy dla towarów śledzonych w partii włączono ujemny poziom zapasów, fakturowanie zamówień odbiorców i fakturowanie zamówień sprzedaży za pośrednictwem księgowania zestawienia nie będzie blokowane dla tych towarów, gdy ilość zapasów będzie równa 0 (zero) lub gdy numer partii będzie niedostępny.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The new functionality uses a default batch ID for the sales lines when batch numbers aren't available.</source><target logoport:matchpercent="0" state="translated">Gdy numery partii są niedostępne, ta nowa funkcjonalność używa dla wierszy sprzedaży domyślnego identyfikatora partii.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>To define the default batch ID that is used for customer orders, on the <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Customer orders<ept id="p2">**</ept> tab, on the <bpt id="p3">**</bpt>Order<ept id="p3">**</ept> FastTab, set the <bpt id="p4">**</bpt>Default batch id<ept id="p4">**</ept> field.</source><target logoport:matchpercent="0" state="translated">Aby zdefiniować domyślny identyfikator partii, który będzie używany dla zamówień odbiorców, na skróconej karcie <bpt id="p3">**</bpt>Zamówienie<ept id="p3">**</ept> na karcie <bpt id="p2">**</bpt>Zamówienia odbiorców<ept id="p2">**</ept> na stronie <bpt id="p1">**</bpt>Parametry sieci sprzedaży<ept id="p1">**</ept> ustaw wartość pola <bpt id="p4">**</bpt>Domyślny identyfikator partii<ept id="p4">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>To define the default batch ID that is used for sales order invoicing through statement posting, on the <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Posting<ept id="p2">**</ept> tab, on the <bpt id="p3">**</bpt>Inventory update<ept id="p3">**</ept> FastTab, set the <bpt id="p4">**</bpt>Default batch id<ept id="p4">**</ept> field.</source><target logoport:matchpercent="79" state="translated" state-qualifier="fuzzy-match">Aby zdefiniować domyślny identyfikator partii, który będzie używany podczas fakturowania zamówień sprzedaży za pośrednictwem fakturowania zestawienia, na skróconej karcie <bpt id="p3">**</bpt>Aktualizacja zapasów<ept id="p3">**</ept> na karcie <bpt id="p2">**</bpt>Księgowanie<ept id="p2">**</ept> na stronie <bpt id="p1">**</bpt>Parametry sieci sprzedaży<ept id="p1">**</ept> ustaw wartość pola <bpt id="p4">**</bpt>Domyślny identyfikator partii<ept id="p4">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>This functionality is available only when advanced warehousing is turned on for the specific store warehouse and items.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ta funkcjonalność jest dostępna tylko wtedy, gdy dla konkretnego magazynu sklepu i towarów jest włączona funkcja zaawansowanego magazynowania.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>In a later release, the functionality will also be supported for scenarios where advanced warehouse management isn't used.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">W późniejszym wydaniu ta funkcjonalność będzie również obsługiwana w scenariuszach, w których nie jest używana funkcja zaawansowanego zarządzania magazynem.</target>
        </trans-unit>
      </group>
    </body>
  </file>
</xliff>