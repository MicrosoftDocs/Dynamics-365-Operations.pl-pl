<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="orderexchanges.md" target-language="pl-PL">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>orderexchanges.ba78aa.43571099727830e81c41416b6fe250dba398b3f8.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>43571099727830e81c41416b6fe250dba398b3f8</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/15/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\orderexchanges.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Configure and process an exchange on a return order</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie i przetwarzanie wymiany w przypadku zamówienia zwrotu</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic explains how to configure an exchange on a return in Microsoft Dynamics 365 for Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym temacie wyjaśniono sposób konfigurowania wymiany w przypadku zwrotu w rozwiązaniu Microsoft Dynamics 365 for Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Configure and process an exchange on a return order</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie i przetwarzanie wymiany w przypadku zamówienia zwrotu</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>In previous versions of Microsoft Dynamics 365 for Retail, returns against customer orders were processed by using the return order document in Retail Headquarters.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W poprzednich wersjach rozwiązania Microsoft Dynamics 365 for Retail zwroty dotyczące zamówień odbiorców były przetwarzane przy użyciu dokumentu zamówienia zwrotu w aplikacji Retail Headquarters.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>However, the return order document can be used to process only products that are being returned.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jednak dokumenty zamówienia zwrotu mogą być używane tylko do przetwarzania produktów zwracanych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>The returned products are indicated by a negative quantity on the return order lines.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zwracane produkty są oznaczone ilością ujemną w wierszach zamówień zwrotu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>By contrast, sales are indicated by a positive quantity.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Z drugiej strony sprzedaż jest wskazywana przez ilość dodatnią.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>However, the return order document doesn't support positive quantities.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dokument zamówienia zwrotu nie obsługuje jednak ilości dodatnich.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Because of this limitation, previous versions of Retail didn't support scenarios where product exchanges are done by using the return order document.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ze względu na to ograniczenie w poprzednich wersjach aplikacji Retail nie była obsługiwane sytuacje, w których wymiana produktu była dokonywana przy użyciu dokumentu zamówienia zwrotu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>However, functionality has been added to support scenarios where exchanges are done on return orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dodano jednak funkcję w celu obsługi sytuacji, w których wymiana odbywa się z wykorzystaniem zamówień zwrotu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Retail now uses the sales order document instead of the return order document to process these types of transactions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby przetwarzać tego typu transakcje w aplikacji Retail jest obecnie używany dokument zamówienia sprzedaży zamiast dokumentu zamówienia zwrotu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>Configure Retail to support exchanges on return orders</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie aplikacji Retail pod kątem obsługi wymiany w przypadku zamówień zwrotu</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Follow these steps to configure the system to support exchanges on return orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby skonfigurować system do obsługi wymiany w przypadku zamówień zwrotu, należy wykonać poniższe czynności.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Go to <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Headquarters setup <ph id="ph2">\&gt;</ph> Parameters <ph id="ph3">\&gt;</ph> Retail parameters<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kliknij kolejno opcje <bpt id="p1">**</bpt>Handel detaliczny <ph id="ph1">\&gt;</ph> Ustawienia centrali <ph id="ph2">\&gt;</ph> Parametry <ph id="ph3">\&gt;</ph> Parametry sieci sprzedaży<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>On the <bpt id="p1">**</bpt>Customer orders<ept id="p1">**</ept> FastTab, set the <bpt id="p2">**</bpt>Process return orders as sales orders<ept id="p2">**</ept> option to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na skróconej karcie <bpt id="p1">**</bpt>Zamówienia odbiorcy<ept id="p1">**</ept> ustaw wartość <bpt id="p3">**</bpt>Tak<ept id="p3">**</ept> opcji <bpt id="p2">**</bpt>Przetwarzanie zamówień zwrotu jako zamówień sprzedaży<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Run the <bpt id="p1">**</bpt>Global configuration distribution schedule<ept id="p1">**</ept> job (<bpt id="p2">**</bpt>1110<ept id="p2">**</ept>).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Uruchom zadanie <bpt id="p1">**</bpt>Harmonogram dystrybucji konfiguracji globalnej<ept id="p1">**</ept> (<bpt id="p2">**</bpt>1110<ept id="p2">**</ept>).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Make an exchange</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dokonywanie wymiany</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>After the system is configured as described in the previous section, the point of sale (POS) user will still select a sales order or sales invoice to process a return, as in previous versions of Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po skonfigurowaniu systemu w sposób opisany w poprzedniej sekcji użytkownik punktu sprzedaży (POS), aby przetworzyć zwrot, będzie w dalszym ciągu musiał wybrać zamówienie sprzedaży lub fakturę sprzedaży, podobnie jak w poprzednich wersjach aplikacji Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>However, after the return items are added to the cart, the user will be able to add new sales lines to the cart.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jednak po dodaniu zwracanych towarów do koszyka, użytkownik będzie mógł dodawać nowe wiersze sprzedaży do koszyka.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>For these new sales lines, the user must define all the attributes that are required in order to process a customer order line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dla tych nowych wierszy sprzedaży użytkownik musi zdefiniować wszystkie atrybuty, które są wymagane w celu przetworzenia wiersza zamówienia odbiorcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>These attributes include the delivery method and fulfillment location.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Do tych atrybutów należy metoda dostawy i lokalizacja realizacji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>The payment that is due for the transaction will be a net of the return order lines and sales order lines.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Płatność należna za transakcję będzie kwotą netto wierszy zamówienia zwrotu i wierszy zamówienia sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>When payment is tendered for the transaction, the return order will be posted as a sales order document in Retail Headquarters, and the system will immediately invoice the return lines.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po przekazaniu płatności za transakcję zamówienie zwrotu zostanie zaksięgowane w aplikacji Retail Headquarters jako dokument zamówienia sprzedaży, a w systemie zostanie natychmiast wystawiona faktura dotycząca wierszy zwrotu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>To provide better visibility into the various amounts for the cart, three new amount fields have been added to the cart.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby zapewnić lepszą widoczność różnych kwot w koszyku, zostały w nim dodane trzy nowe pola kwoty.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>You can use the screen designer to make these new fields available in the POS user interface (UI).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W celu udostępnienia tych nowych pól w interfejsie użytkownika (UI) punktu sprzedaży można użyć projektanta układu ekranu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source><bpt id="p1">**</bpt>Deposit applied<ept id="p1">**</ept> – The deposit amount that is applied on a transaction when the user does a customer order pickup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Zastosowana kaucja<ept id="p1">**</ept> — kwota kaucji, która jest stosowana do transakcji, gdy użytkownik pobiera zamówienie odbiorcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>If there is no deposit override, and a 10-percent deposit is configured, the amount in this field is 90 percent of the total amount of the customer order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli nie określono żadnych zastąpień kaucji oraz została skonfigurowana kaucja 10-procentowa, to kwota w tym polu stanowi 90 procent sumy zamówienia odbiorcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source><bpt id="p1">**</bpt>Carry out amount<ept id="p1">**</ept> – The total amount for lines where the delivery mode was set to <bpt id="p2">**</bpt>Carry out<ept id="p2">**</ept> when the customer order was created or edited, or during a customer order exchange.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Kwota zrealizowana<ept id="p1">**</ept> — łączna kwota dla wierszy, w których ustawiono metodę dostawy <bpt id="p2">**</bpt>Wyniesienie<ept id="p2">**</ept>, gdy zamówienie klienta zostało utworzone lub zmodyfikowane albo podczas wymiany zamówienia odbiorcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>The amount in this field includes taxes and charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kwota w tym polu obejmuje podatki i opłaty.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source><bpt id="p1">**</bpt>Return amount<ept id="p1">**</ept> – The total amount for lines that have negative quantities during the customer order exchange.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Kwota zwrotu<ept id="p1">**</ept> — suma dla wierszy, które zawierają ilości ujemne podczas wymiany zamówienia odbiorcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>The amount in this field includes taxes and charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kwota w tym polu obejmuje podatki i opłaty.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>