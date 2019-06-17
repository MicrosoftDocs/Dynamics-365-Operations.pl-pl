<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="omni-auto-charges.md" target-language="pl-PL">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>omni-auto-charges.2f6e37.47829a6fcae37e03510929dc46b942455016df0b.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>47829a6fcae37e03510929dc46b942455016df0b</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>ffc37f7c2a63bada3055f37856a30424040bc9a3</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/16/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\omni-auto-charges.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Omni-channel advanced auto charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wielokanałowe zaawansowane opłaty automatyczne</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes capabilities for managing additional order charges for Retail channel orders using advanced auto charges features.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym temacie opisano funkcje zarządzania opłatami za dodatkowe zamówienia dla zamówień kanału Retail przy użyciu zaawansowanych funkcji opłat automatycznych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Omni-channel advanced auto charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wielokanałowe zaawansowane opłaty automatyczne</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>This topic provides information on configuration and deployment of the advanced auto-charges feature which are available in Dynamics 365 for Retail version 10.0.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ten temat zawiera informacje o konfiguracji i wdrażaniu funkcji zaawansowanych opłat automatycznych, które są dostępne w programie Dynamics 365 for Retail w wersji 10.0.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>When the advanced auto-charges features are enabled, orders created in any supported Retail channel (point of sale (POS), call center, and online), can take advantage of the <bpt id="p1">[</bpt>auto-charges<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> configurations defined in the ERP application for both header and line-level related charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po włączeniu funkcji zaawansowanych automatycznych opłat zamówienia utworzone w dowolnym obsługiwanym kanale Retail (punkt sprzedaży (POS), biuro obsługi i w trybie online), można korzystać z <bpt id="p1">[</bpt>automatycznych opłat<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> zdefiniowanych w aplikacji ERP dla opłat dotyczących zarówno poziomu nagłówka, jak i wiersza.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>In releases prior to Dynamics 365 for Retail version 10.0, <bpt id="p1">[</bpt>auto-charge<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> configurations are only accessible by orders created in e-Commerce and call center channels.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W programie Dynamics 365 for Retail w wersjach wcześniejszych niż 10.0 konfiguracje <bpt id="p1">[</bpt>opłat automatycznych<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> są dostępne tylko dla zamówień utworzonych w kanałach e-commerce i biura obsługi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>In versions 10.0 and later, POS-created orders can leverage the auto-charges configurations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W wersji 10.0 i nowszej zamówienia utworzone w POS mogą korzystać z konfiguracji opłat automatycznych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>That way, additional miscellaneous charges can systematically be added to sales transactions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W ten sposób dodatkowe opłaty różne mogą być systematycznie dodawane do transakcji sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>When using releases prior to version 10.0, a POS user is prompted to manually enter a shipping fee during the creation of a "ship all" or "ship selected" POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W wersjach wcześniejszych niż 10.0 użytkownik POS otrzymuje monit o ręczne wprowadzenie opłaty transportowej podczas tworzenia transakcji POS „wyślij wszystko” lub „wyślij wybrane”.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>While the miscellaneous charges capabilities of the application are utilized in respect to how the charges are written to the order, no systematic calculation is provided – the calculation relies on the user's input to determine the value of the charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited">Podczas gdy funkcje aplikacji związane z opłatami różnymi są używane w odniesieniu do tego, jak opłaty są zapisywane na zamówieniu, żadne systemowe obliczenia nie są dostarczane — obliczenia polegają na danych podanych przez użytkownika do określenia wartości opłat.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The charges can only be added as a single "shipping" related charges code and cannot easily be edited or changed in the POS after they are created.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Opłaty mogą być dodawane tylko jako jeden kod opłat „transportowych” i nie mogą być łatwo edytowalne ani zmieniane w POS po utworzeniu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>The use of manual prompts to add shipping charges is still available in versions 10.0 and later.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ręczne monity do dodawania opłat transportowych są nadal dostępne w wersjach 10.0 i nowszych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>If an organization does not enable the <bpt id="p1">**</bpt>Advanced Auto-charges<ept id="p1">**</ept> parameter, the POS prompts for manual entry of charges will remain the same.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli organizacja nie obsługuje parametru <bpt id="p1">**</bpt>Zaawansowane opłaty automatyczne<ept id="p1">**</ept>, monity POS o ręczne wprowadzenie zostaną takie same.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>With the advanced auto-charges feature, POS users can have systematic calculations for any defined miscellaneous charges based on auto-charges setup tables.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dzięki funkcji zaawansowanych opłat automatycznych użytkownicy POS mogą korzystać z systemowych kalkulacji dla dowolnych zdefiniowanych opłat różnych na podstawie tabel konfiguracji opłat automatycznych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>In addition, users will have the ability to add or edit an unlimited amount of additional charges and fees to any POS sales transaction at the header or line-level (for a cash and carry or customer order).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ponadto użytkownicy będą mieli możliwość dodawania lub edytowania nieograniczonej ilości dodatkowych opłat i płatności do dowolnej transakcji sprzedaży w POS na poziomie nagłówka lub wiersza (dla transakcji kasowych i lub zamówień odbiorcy).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Enabling advanced auto-charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Włączanie zaawansowanych opłat automatycznych</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>On the <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Headquarters setup <ph id="ph2">\&gt;</ph> Parameters <ph id="ph3">\&gt;</ph> Retail parameters<ept id="p1">**</ept> page, go to the <bpt id="p2">**</bpt>Customer orders<ept id="p2">**</ept> tab. On the <bpt id="p3">**</bpt>Charges<ept id="p3">**</ept> FastTab, set <bpt id="p4">**</bpt>Use advanced auto-charges<ept id="p4">**</ept> to <bpt id="p5">**</bpt>Yes<ept id="p5">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">Na stronie <bpt id="p1">**</bpt>Sprzedaż detaliczna <ph id="ph1">\&gt;</ph> Ustawienia centrali <ph id="ph2">\&gt;</ph> Parametry <ph id="ph3">\&gt;</ph> Parametry sieci sprzedaży<ept id="p1">**</ept> przejdź na kartę <bpt id="p2">**</bpt>Zamówienia odbiorcy<ept id="p2">**</ept>. Na karcie skróconej <bpt id="p3">**</bpt>Opłaty<ept id="p3">**</ept> ustaw opcję <bpt id="p4">**</bpt>Użyj zaawansowanego automatycznego naliczania opłat dodatkowych<ept id="p4">**</ept> na <bpt id="p5">**</bpt>Tak<ept id="p5">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Advanced Auto-Charges Parameter</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Parametr zaawansowanych opłat automatycznych</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>When advanced auto-charges are enabled, users are no longer prompted to manually enter a shipping charge at the POS terminal when creating a ship-all or ship-selected customer order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po włączeniu zaawansowanych opłat automatycznych użytkownicy nie są już monitowani o ręczne wprowadzanie opłat transportowych na terminalu POS podczas tworzenia zamówienia odbiorcy „wyślij wszystko” lub „wyślij wybrane”.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>POS order charges are systematically calculated and added to the POS transaction (if a corresponding auto-charges table that matches the criterion of the order being created are found).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Opłaty za zamówienie POS są systemowo obliczane i dodawane do transakcji POS (w przypadku znalezienia odpowiedniej tabeli opłat automatycznych pasującej do kryteriów tworzonego zamówienia).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Users can also add or maintain header or line-level charges manually through newly added POS operations that can be added to the POS screen layouts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Użytkownik może również dodawać i obsługiwać opłaty na poziomie nagłówka lub wiersza ręcznie za pośrednictwem nowo dodanych operacji POS, które mogą być dodane do układów ekranu POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>When advanced auto-charges are enabled, the existing <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> for <bpt id="p2">**</bpt>Shipping charges code<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Refund shipping charges<ept id="p3">**</ept> are no longer utilized.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po włączeniu zaawansowanych opłat automatycznych, istniejące <bpt id="p1">**</bpt>Parametry sieci sprzedaży<ept id="p1">**</ept> dla <bpt id="p2">**</bpt>Kodu opłat transportowych<ept id="p2">**</ept> i <bpt id="p3">**</bpt>Zwrotu opłat transportowych<ept id="p3">**</ept> nie są używane.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>These parameters are only applicable if the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is set to <bpt id="p2">**</bpt>No<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Parametry te mają zastosowanie tylko wtedy jeśli parametr <bpt id="p1">**</bpt>Użyj zaawansowanego automatycznego naliczania opłat dodatkowych<ept id="p1">**</ept> ma wartość <bpt id="p2">**</bpt>Nie<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Before you enable this feature, ensure that you have tested and trained your employees, as this will change the business process flow of how shipping or other charges are calculated and added to POS sales orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przed włączeniem tej funkcji należy upewnić się, że pracownicy przeszli szkolenie, ponieważ ta funkcja zmienia przepływ procesu biznesowego w odniesieniu do metody obliczania opłat transportowych i innych i ich dodawania do zamówień sprzedaży POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Make sure that you understand the impact of the process flow to the creation of transactions from POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Upewnij się, że rozumiesz wpływ przepływu procesu na tworzenie transakcji w POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>For call center and e-Commerce orders, the impact of enabling advanced auto-charges is minimal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W przypadku zamówień składanych przez biuro obsługi i w witrynie e-Commerce wpływ włączania zaawansowanych automatycznych opłat dodatkowych jest minimalny.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>Call center and e-Commerce applications will continue to have the same behavior they have had historically related to the auto-charges tables to calculate additional order fees.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aplikacje biura obsługi i e-Commerce nadal będą zachowywać się tak samo jak wcześniej w odniesieniu do tabel automatycznych opłat dodatkowych do obliczenia dodatkowych opłat za zamówienia.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>Call center channel users will continue to have the ability to manually edit any system calculated auto-charges at the header or line level, or manually add additional miscellaneous charges at the header or line level.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Użytkownicy kanału biura obsługi będą nadal mieć możliwość ręcznej edycji dowolnych obliczonych przez system automatycznych opłat dodatkowych na poziomie nagłówka lub wiersza lub ręcznego dodawania dodatkowych opłat różnych na poziomie nagłówka lub wiersza.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Additional POS operations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dodatkowe operacje POS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>For advanced auto-charges to work properly in your POS application environment, new POS operations have been added.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby zaawansowane automatyczne opłaty dodatkowe działały prawidłowo w środowisku aplikacji POS, dodano nowe operacje POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>These operations must be added to your <bpt id="p1">[</bpt>POS screen layouts<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> and deployed to the POS devices as you deploy advanced auto-charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Te operacje muszą być dodane do <bpt id="p1">[</bpt>układów ekranu POS<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> i wdrożone na urządzeniach POS razem z zaawansowanymi automatycznymi opłatami dodatkowymi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>If these operations are not added, users will not be able to manage or maintain miscellaneous charges on the POS transactions and will have no way of adjusting or changing the charges values that are systematically calculated based on auto-charges configurations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli te operacje nie zostaną dodane, użytkownicy nie będzie mogli zarządzać ani obsługiwać opłat dodatkowych w transakcjach POS i nie będą mogli korygować ani zmieniać wartości opłat dodatkowych, które są systematycznie obliczane na podstawie konfiguracji automatycznych opłat dodatkowych</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>At minimum, it is suggested that you deploy the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation to your POS layout.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Co najmniej zaleca się wdrożenie operacji <bpt id="p1">**</bpt>Zarządzaj opłatami dodatkowymi<ept id="p1">**</ept> do układu POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>The new operations are as follows.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Oto nowe operacje:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source><bpt id="p1">**</bpt>142 - Manage charges<ept id="p1">**</ept> – Use this operation to allow POS users to view and edit miscellaneous charges for the POS transaction that were either added manually or systematically through auto-charges calculations.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>142 — Zarządzaj opłatami dodatkowymi<ept id="p1">**</ept> — umożliwia użytkownikom POS wyświetlanie i edytowanie opłat dodatkowych dla transakcji w POS, które zostały dodane ręcznie lub systemowo przy użyciu obliczeń automatycznych opłat dodatkowych.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source><bpt id="p1">**</bpt>141 - Add header charges<ept id="p1">**</ept> – Use this operation to give the user the ability to manually add a header-level miscellaneous charge to any POS sales transaction (and select the charges code to be used).</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>141 — Dodaj opłaty na poziomie nagłówka<ept id="p1">**</ept> — umożliwia użytkownikowi ręcznie dodawanie opłaty dodatkowej na poziomie nagłówka do dowolnej transakcji POS (i wybranie kodu opłaty, który ma zostać użyty).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source><bpt id="p1">**</bpt>140 - Add line charges<ept id="p1">**</ept> – Use this operation to give the user the ability to manually add a line level miscellaneous charge to any POS sales transaction line (and select the charges code to be used).</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>140 — Dodaj opłaty na poziomie wiersza<ept id="p1">**</ept> — umożliwia użytkownikowi ręcznie dodawanie opłaty dodatkowej na poziomie wiersza do dowolnego wiersza transakcji POS (i wybranie kodu opłaty, który ma zostać użyty).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source><bpt id="p1">**</bpt>143 - Recalculate charges<ept id="p1">**</ept> – Use this operation to perform a full re-calculation of the charges for the sales transaction.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>143 — Oblicz ponownie opłaty<ept id="p1">**</ept> — umożliwia wykonanie pełnego ponownego obliczania opłat dla transakcji sprzedaży.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Any previously user-overwritten auto-charges will be recalculated based on the current cart configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wszystkie wcześniej zastąpione przez użytkownika automatyczne opłaty dodatkowe zostaną przeliczone na podstawie bieżącej konfiguracji koszyka.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>As with all POS operations, security configurations can be made to require manager approval in order to execute the operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tak jak w przypadku wszystkie operacji POS konfiguracja zabezpieczeń może również wymagać zatwierdzenia menedżera w celu wykonania operacji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>It is important to note that the above listed POS operations can also be added to the POS layout even if the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Należy zwrócić uwagę, że powyżej wymienione operacje punktu sprzedaży można również dodawać do układu punktu sprzedaży nawet wtedy, gdy jest wyłączony parametr <bpt id="p1">**</bpt>Użyj zaawansowanego automatycznego naliczania opłat dodatkowych<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>In this scenario, organizations will still get added benefits of being able to view manually added charges and edit them using the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym scenariuszu, organizacje będą nadal korzystać z dodanych udogodnień w postaci możliwości wyświetlenia recznie dodanych opłat i edytowania ich za pomocą operacji <bpt id="p1">**</bpt>Zarządzaj opłatami<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>Users may also use the <bpt id="p1">**</bpt>Add header charges<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Add line charges<ept id="p2">**</ept> operations for POS transactions even when <bpt id="p3">**</bpt>Use advanced auto-charges<ept id="p3">**</ept> parameter is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Użytkownicy mogą również korzystać z operacji <bpt id="p1">**</bpt>Dodaj opłaty z nagłówka<ept id="p1">**</ept> i <bpt id="p2">**</bpt>dodaj opłaty z wiersza<ept id="p2">**</ept> dla transakcji w punkcie sprzedaży, nawet wówczas, gdy jest wyłączony parametr <bpt id="p3">**</bpt>Użyj zaawansowanego automatycznego naliczania opłat dodatkowych<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>The <bpt id="p1">**</bpt>Recalculate charges<ept id="p1">**</ept> operation has less functionality if used when <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Operacja <bpt id="p1">**</bpt>Ponownie Oblicz opłaty<ept id="p1">**</ept> ma mniej funkcji, kiedy parametr <bpt id="p2">**</bpt>Użyj zaawansowanego automatycznego naliczania opłat dodatkowych<ept id="p2">**</ept> jest wyłączony.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>In this sceanrio, nothing would be recalculated and any charges manually added to the transaction would just reset to $0.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym scenariuszu nie będziemy niczego ponownie przeliczać, a opłaty dodane ręcznie do transakcji zostaną zresetowane do wartości $0.00.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>Use case examples</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przykłady zastosowania</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>In this section, sample use cases are presented to help you understand the configuration and usage of auto-charges and miscellaneous charges within the context of Retail channel orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tej sekcji pokazano przykładu zastosowania, które pomogą zrozumieć konfigurację i używać automatycznych opłat dodatkowych i opłat różnych w kontekście zamówień w kanale sieci sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>These examples illustrate the behavior of the application when the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter has been enabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Następujące przykłady przedstawiają sposób działania aplikacji po włączeniu parametru <bpt id="p1">**</bpt>Użyj zaawansowanego automatycznego naliczania opłat dodatkowych<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Auto-charges header charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przykład automatycznych opłat dodatkowych na poziomie nagłówka</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Scenariusz użycia</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>A retailer wants to automatically add charges for freight when transactions are created in any Retail channel that require a shipment of products to the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sprzedawca chce automatycznie dodać opłaty za transport podczas tworzenia transakcji w dowolnym kanale sieci sprzedaży, który wymaga wysyłki produktów do odbiorcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>The retailer offers 2 methods of delivery: Ground and Air.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sprzedawca oferuje 2 metody dostawy: drogą lądową i powietrzną.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>If a customer chooses Ground delivery and the order value is less than $100, the retailer wants to charge the customer a freight charge of $10.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli odbiorca wybierze dostawę drogą lądową, a wartość zamówienia jest mniejsza niż $100, sprzedawca chce naliczać opłatę transportową $10,00.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>If the order is over $100 in value and the customer chooses ground shipping, the customer will not be charged any additional freight fees.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli wartość zamówienia przekracza $100 i odbiorca wybierz dostawę drogą lądową, odbiorca nie zostanie obciążony żadnymi dodatkowymi opłatami transportowymi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>If the customer chooses the Air method of delivery for all orders, regardless of their total value, will be charged a freight fee of $20.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli odbiorca zdecyduje się na transport lotniczy dla wszystkich zleceń, niezależnie od ich łącznej wartości zostanie naliczona opłata transportowa w wysokości $20.00.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Instalacja i konfiguracja</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>This scenario requires the configuration of two auto-charges tables.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ten scenariusz wymaga wcześniejszego skonfigurowania dwóch tabel automatycznych opłat dodatkowych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Go to <bpt id="p1">**</bpt>Accounts receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Auto charges<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz kolejno opcje <bpt id="p1">**</bpt>Rozrachunki z odbiorcami <ph id="ph1">\&gt;</ph> Ustawienia opłat <ph id="ph2">\&gt;</ph> Opłaty automatyczne<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Configure two different header-level auto charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie dwóch różnych automatycznych opłat na poziomie nagłówka.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Configure one for the "Ground mode" of delivery and one for the "Air mode" of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skonfiguruj jedną opłatę dla „dostawy lądowej” i drugą dla „dostawy lotniczej”.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>For this scenario, configure them to be used for "All customers".</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym scenariuszu skonfigurujemy je do użycia dla „Wszystkich odbiorców”.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>For the ground delivery charges, in the lines section of the <bpt id="p1">**</bpt>Auto-charges<ept id="p1">**</ept> page, define a charge that will be applied for orders between $.01 and $100 as $10.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dla opłaty za dostawę lądową w sekcji wierszy na stronie <bpt id="p1">**</bpt>Opłaty automatyczne<ept id="p1">**</ept> zdefiniuj opłatę $10.00. , która zostanie zastosowana do zleceń o wartości od $0,01 do $100.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>Create another charges line to indicate orders over $100.01 will have no charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Utwórz kolejny wiersz opłaty dla zamówień o wartości powyżej $100.01, dla których nie będą naliczane żaden opłaty.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>Auto charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przykład opłat automatycznych</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>For the air delivery charges, in the lines section of the auto-charges form, define a charge of $20.00 that will be applied to all orders (between a value of $.01 to $9,999,999).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dla opłaty za dostawę lotniczą w sekcji wierszy na stronie opłat automatycznych zdefiniuj opłatę $20.00, która zostanie zastosowana do wszystkich zleceń (o wartości od $0,01 to $9 999 999).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Send the changes to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wyślij zmiany do bazy danych serwera/kanału Retail, aby można było używać ich w POS za pomocą zadania <bpt id="p1">**</bpt>Harmonogram dystrybucji 1040<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>Sales processing for this scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przetwarzanie sprzedaży w tym scenariuszu</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>After the configuration steps above are complete and the changes have been applied to the channel database, any customer order or sales transaction created in the POS, call center, or e-Commerce channels that have the ground or air delivery methods set at the header level will utilize these charges and automatically apply them to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po wykonaniu powyższej procedury konfiguracyjnej i zastosowaniu zmian do bazy danych kanału, wszelkie zamówienia odbiorcy lub transakcje sprzedaży utworzone w POS, biurze sprzedaży lub kanałach e-Commerce, które mają dostawę lądową lub lotniczą ustawioną na poziomie nagłówka, będą używać tych opłat i stosować je do sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>At this time the charges will apply to all sales transactions created within the legal entity that utilize these delivery modes, as there is no functionality to designate that an auto-charge configuration will only apply to a specific selling channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Obecnie opłaty będą stosowane do wszystkich transakcji sprzedaży utworzonych w obrębie firmy korzystającej z tych metod dostawy, ponieważ nie ma w tej chwili funkcji, która pozwalałaby przydzielić konfigurację automatycznych opłat dodatkowych tylko do określonego kanału sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>For POS and e-Commerce scenarios, because there is no clearly defined "header" on these orders, header-level charges will only apply if all sales lines on the transaction are set to ship with the exact same mode of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W scenariuszach POS i e-Commerce, ponieważ nie istnieje żaden ściśle określony „nagłówek” na tych zamówieniach, opłaty na poziomie nagłówka będą miały zastosowanie tylko jeśli wszystkie wiersze sprzedaży w odniesieniu do transakcji mają identyczną metodą dostawy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>If there are "mixed-modes" of fulfillment on the transactions created by POS or e-Commerce, only line-level auto-charges will be considered and applied.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W przypadku „mieszanej metody” realizacji transakcji utworzonych w POS lub e-Commerce, tylko automatyczne opłaty na poziomie wiersza będą brane pod uwagę i stosowane.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>In call center scenarios, the user has control over the setting of the delivery mode at the order header, therefore header-level charges will apply for these orders even if some of the sales lines have been configured to use a different mode of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W scenariuszach biura obsługi użytkownik ma kontrolę nad ustawieniem metody dostawy w nagłówku zamówienia, więc opłaty na poziomie nagłówka będą dotyczyć tych zamówień nawet wtedy, gdy niektóre wiersze sprzedaży zostały skonfigurowane z innym trybem dostawy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Header-level charges for call center orders will always be based on the mode of delivery that is defined at the order header level of the sales order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Opłaty na poziomie nagłówka dla zamówień w biurze obsługi zawsze będą oparte na trybie dostawy, który jest zdefiniowany na poziomie nagłówka zamówienia sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>Auto-charges line charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przykład automatycznych opłat dodatkowych na poziomie wiersza</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Scenariusz użycia</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>A retailer wants to add an additional charge to the customer for setup fees when the customer purchases a particular model of computer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sprzedawca chce dodać dodatkową opłatę dla odbiorcy za konfigurację, gdy odbiorca kupuje konkretny model komputera.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>This computer requires additional non-optional setup actions that the retailer will perform for the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ten komputer wymaga dodatkowej konfiguracji, która nie jest opcjonalna i którą sprzedawca wykona dla odbiorcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>The retailer has informed customers that there will be an additional fee for this setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sprzedawca poinformował odbiorców, że za tę konfigurację naliczana jest dodatkowa opłata.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>The retailer prefers to manage the charges related to this fee separately from the product sales price for financial reporting purposes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sprzedawca woli zarządzać opłatami związanymi z tą opłatą oddzielnie od ceny sprzedaży produktu ze względu na wymagania sprawozdawczości finansowej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>A setup fee of $19.99 will be charged to the customer when this specific computer is purchased in any retail channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Opłata za konfigurację wynosi $19,99 i odbiorca zostania nią obciążony w chwili zakupu tego komputera w dowolnym kanale sieci sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Instalacja i konfiguracja</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>This scenario requires the configuration of one line-level auto charges table.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ten scenariusz wymaga wcześniejszego skonfigurowania tabeli automatycznych opłat dodatkowych na poziomie wiersza.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>Go to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Auto charges<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz kolejno opcje <bpt id="p1">**</bpt>Rozrachunki z odbiorcami <ph id="ph1">\&gt;</ph> Ustawienia opłat <ph id="ph2">\&gt;</ph> Opłaty automatyczne<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>Set the <bpt id="p1">**</bpt>Level<ept id="p1">**</ept> drop-down menu to <bpt id="p2">**</bpt>Line<ept id="p2">**</ept>, and create a new auto-charges record for all customers and for the specific product or product group where the setup fees will be charged.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W menu rozwijanym <bpt id="p1">**</bpt>Poziom<ept id="p1">**</ept> wybierz wartość <bpt id="p2">**</bpt>Wiersz<ept id="p2">**</ept> i utwórz nowy rekord automatycznej opłaty dodatkowej dla wszystkich odbiorców i dla konkretnego produktu lub grupy produktów, w których będzie naliczana opłata konfiguracyjna.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>Auto charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przykład opłat automatycznych</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wyślij opłaty do bazy danych serwera/kanału Retail, aby można było używać ich w POS za pomocą zadania <bpt id="p1">**</bpt>Harmonogram dystrybucji 1040<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>Sales processing for this scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przetwarzanie sprzedaży w tym scenariuszu</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>After the configurations steps above are complete and the changes have been applied to the channel database, any customer order or sales transaction created in the POS, call center, or e-Commerce channels that have this item on the order will trigger a line-level charge to be systematically added to the order total.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po wykonaniu powyższej procedury konfiguracyjnej i zastosowaniu zmian do bazy danych kanału, wszelkie zamówienia odbiorcy lub transakcje sprzedaży utworzone w POS, biurze sprzedaży lub kanałach e-Commerce, które mają tę pozycję na zamówieniu, będą uruchamiały opłatę na poziomie wiersza, która będzie systemowo dodawana do sumy zamówienia.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>At this time the charges will apply to any sales line that matches the configuration of the line-level auto charges within the legal entity, as there is no functionality to configure a line-level auto-charge to apply only to a specific selling channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Obecnie opłaty będą stosowane do wszystkich wierszy sprzedaży pasujących do konfiguracji automatycznych opłat dodatkowych na poziomie wiersza w obrębie firmy, ponieważ nie ma w tej chwili funkcji, która pozwalałaby skonfigurować automatyczne opłaty dodatkowe w taki sposób, aby miały zastosowanie do określonego kanału sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Manual header charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przykład opłat ręcznych na poziomie nagłówka</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>Use case scenario description</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Opis scenariusza użycia</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>A retailer is making an exception to typical processes by offering to provide a special home delivery of products to a customers who order products in the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sprzedawca robi wyjątek od typowych procesów, oferując specjalną dostawę do domu produktów odbiorcom, którzy zamówili produkty w sklepie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>The retailer and the customer have agreed that the customer will pay an additional $25 handling fee for this service.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sprzedawca i odbiorca zgadzają się, odbiorca zapłaci dodatkowe $25 opłaty za tę usługę.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>The order-taker needs to add this additional fee to the transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Osoba przyjmująca zamówienie musi dodać tę opłatę dodatkową do transakcji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>Because the fee is a blanket fee and not related to any single product on the order, a header charge will be utilized.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ponieważ opłata jest opłatą zbiorczą i nie jest związana z żadnym jednym produktem na zamówieniu, zostanie zastosowana opłata na poziomie nagłówka.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Instalacja i konfiguracja</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>Ensure the charges code that will be used in this scenario has been properly configured by going to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Charges<ept id="p1">**</ept> to define an appropriate charges code for the scenario.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Upewnij się, kod opłat, który będzie używany w tym scenariuszu, został poprawnie skonfigurowany w <bpt id="p1">**</bpt>Rozrachunki z odbiorcami <ph id="ph1">\&gt;</ph> Ustawienia opłat <ph id="ph2">\&gt;</ph> Opłaty<ept id="p1">**</ept>, aby zdefiniować odpowiedni kod opłat dla tego scenariusza.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>Charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przykład opłat</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>If the charge should be considered a "shipping" related charge for the purpose of shipping related discounts or promotions, set <bpt id="p1">**</bpt>Shipping charge<ept id="p1">**</ept> on the charges code to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited">Jeśli opłata powinna być traktowana jako opłata związana z „wysyłką” do celów związanych rabatami wysyłkowymi lub promocjami, ustaw <bpt id="p1">**</bpt>Opłatę wysyłkową<ept id="p1">**</ept> w kodzie opłaty na <bpt id="p2">**</bpt>Tak<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>If this charge is also allowed to be systematically refunded during the processing of a return transaction in the POS application, set <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli ta opłata jest również dozwolona do systemowego zwrotu podczas przetwarzania transakcji zwrotu w aplikacji POL, ustaw <bpt id="p1">**</bpt>Zwrot<ept id="p1">**</ept> na <bpt id="p2">**</bpt>Tak<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>The <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag is only applicable when the <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> parameter is set to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Flaga <bpt id="p1">**</bpt>Zwrot<ept id="p1">**</ept> ma zastosowanie tylko wtedy, gdy parametr <bpt id="p2">**</bpt>Użyj zaawansowanego automatycznego naliczania opłat dodatkowych<ept id="p2">**</ept> ma wartość <bpt id="p3">**</bpt>Tak<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wyślij opłaty do bazy danych serwera/kanału Retail, aby można było używać ich w POS za pomocą zadania <bpt id="p1">**</bpt>Harmonogram dystrybucji 1040<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>The <bpt id="p1">**</bpt>Add header charge<ept id="p1">**</ept> operation must be configured in your <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a button that is accessible to the user from POS can call this operation (operation 141).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Operacja <bpt id="p1">**</bpt>Dodaj opłaty z nagłówka<ept id="p1">**</ept> musi być skonfigurowana w <bpt id="p2">[</bpt>układzie ekranu POS<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept>, aby przycisk dostępny dla użytkownika z poziomu POS mógł wywoływać tę operację (operacja 141).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>The screen layout changes must be distributed to the retail channel as well through the distribution schedule function.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zmiany układu ekranu muszą być rozdzielone do kanałów sieci sprzedaży, jak również za pomocą funkcji harmonogramu dystrybucji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>Sales processing of manual header charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przetwarzanie sprzedaży ręcznych opłat na poziomie nagłówka</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>To execute the scenario in the POS application, the POS user will create the sales transaction as usual, adding the products and any other configurations to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Do wykonania tego scenariusza w aplikacji POS, użytkownik POS musi utworzyć transakcję sprzedaży w zwykły sposób, dodając produkty i wszelkie inne konfiguracje do sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>Prior to collecting payment, the user should execute the <bpt id="p1">**</bpt>Add header charge<ept id="p1">**</ept> operation, which will prompt the user to select a charges code and enter the charges value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przed pobraniem płatności użytkownik powinien wykonać operację <bpt id="p1">**</bpt>Dodaj opłatę na poziomie nagłówka<ept id="p1">**</ept>, która będzie monitować użytkownika o wybranie kodu opłat i wprowadzenie wartości opłat.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>Once the user completes the process, the charge will be added to the sales order as a header-level charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gdy użytkownik zakończy ten proces, opłata zostanie dodana do zamówienia sprzedaży jako opłata na poziomie nagłówka.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>This process can be applied in the call center by using the existing <bpt id="p1">**</bpt>Charges<ept id="p1">**</ept> feature found on the <bpt id="p2">**</bpt>Sell<ept id="p2">**</ept> tab on the toolbar.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ten proces może być zastosowany w biurze obsługi za pomocą istniejącej funkcji <bpt id="p1">**</bpt>Opłaty<ept id="p1">**</ept> na karcie <bpt id="p2">**</bpt>Sprzedaż<ept id="p2">**</ept> na pasku narzędzi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>On the <bpt id="p1">**</bpt>Maintain charges<ept id="p1">**</ept> page, the user can add a new charges line to the order header.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na karcie <bpt id="p1">**</bpt>Obsługa opłat<ept id="p1">**</ept> użytkownik może dodać nowy wiersz opłaty do nagłówka zamówienia.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>Manual line charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przykład opłat ręcznych na poziomie wiersza</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Scenariusz użycia</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>A customer has requested that 2 of the 5 items on their sales order be gift-wrapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Odbiorca poprosił o zapakowanie na prezent 2 z 5 towarów z zamówienia sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>The retailer offers this optional service for a fee of $2.00 per item.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sprzedawca oferuje taką usługę za opłatą $2,00 za przedmiot.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>The order-taker will need to add these fees to the specific items that need to be gift-wrapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Osoba przyjmująca zamówienie musi dodać te opłaty do określonego towaru, które muszą zostać zapakowane na prezent.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Instalacja i konfiguracja</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>Ensure the charges code that will be used in this scenario has been properly configured by going to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Charges<ept id="p1">**</ept> to define an appropriate charges code for the scenario.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Upewnij się, kod opłat, który będzie używany w tym scenariuszu, został poprawnie skonfigurowany w <bpt id="p1">**</bpt>Rozrachunki z odbiorcami <ph id="ph1">\&gt;</ph> Ustawienia opłat <ph id="ph2">\&gt;</ph> Opłaty<ept id="p1">**</ept>, aby zdefiniować odpowiedni kod opłat dla tego scenariusza.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>If the charge should be considered a "shipping" related charge for the purpose of shipping related discounts or promotions, set the <bpt id="p1">**</bpt>Shipping charge<ept id="p1">**</ept> on the charges code to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli opłata powinna być traktowana jako opłata związana z „wysyłką” do celów związanych rabatami wysyłkowymi lub promocjami, ustaw <bpt id="p1">**</bpt>Opłatę wysyłkową<ept id="p1">**</ept> w kodzie opłaty na <bpt id="p2">**</bpt>Tak<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>If the charge is also allowed to be systematically refunded during the processing of a return transaction in the POS application, set <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli ta opłata jest również dozwolona do systemowego zwrotu podczas przetwarzania transakcji zwrotu w aplikacji POL, ustaw <bpt id="p1">**</bpt>Zwrot<ept id="p1">**</ept> na <bpt id="p2">**</bpt>Tak<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source>The <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag is only applicable when the <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> parameter is set to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Flaga <bpt id="p1">**</bpt>Zwrot<ept id="p1">**</ept> ma zastosowanie tylko wtedy, gdy parametr <bpt id="p2">**</bpt>Użyj zaawansowanego automatycznego naliczania opłat dodatkowych<ept id="p2">**</ept> ma wartość <bpt id="p3">**</bpt>Tak<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wyślij opłaty do bazy danych serwera/kanału Retail, aby można było używać ich w POS za pomocą zadania <bpt id="p1">**</bpt>Harmonogram dystrybucji 1040<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>The <bpt id="p1">**</bpt>Add line charge<ept id="p1">**</ept> operation must be configured in your <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a button that is accessible to the user from POS can call this operation (operation 140).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Operacja <bpt id="p1">**</bpt>Dodaj opłaty z wiersza<ept id="p1">**</ept> musi być skonfigurowana w <bpt id="p2">[</bpt>układzie ekranu POS<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept>, aby przycisk dostępny dla użytkownika z poziomu POS mógł wywoływać tę operację (operacja 140).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>The screen layout changes must be distributed to the retail channel as well through the distribution schedule function.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zmiany układu ekranu muszą być rozdzielone do kanałów sieci sprzedaży, jak również za pomocą funkcji harmonogramu dystrybucji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>Sales processing of the manual line charge</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przetwarzanie sprzedaży ręcznej opłaty na poziomie wiersza</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source>To execute the scenario in the POS application, the POS user will create the sales transaction as usual, adding the products and any other configurations to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Do wykonania tego scenariusza w aplikacji POS, użytkownik POS musi utworzyć transakcję sprzedaży w zwykły sposób, dodając produkty i wszelkie inne konfiguracje do sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source>Prior to collecting payment, the user should select the specific line where the charge will apply from the POS item list display and execute the <bpt id="p1">**</bpt>Add line charge<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przed pobieraniem płatności użytkownik powinien wybrać określony wiersz, w którym będą stosowane opłaty z listy pozycji POS i wykonać operację <bpt id="p1">**</bpt>Dodaj opłatę na poziomie wiersza<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source>The user will be prompted to select a charges code and enter the charges value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Użytkownik zobaczy monit o wybranie kod opłaty i wprowadzenie wartości opłat.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>Once the user completes the process, the charge will be linked to the line and added to the order total as a line level charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gdy użytkownik zakończy ten proces, opłata zostanie połączona z wierszem i dodana do sumy zamówienia jako opłata na poziomie wiersza.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>The user can repeat the process to add additional line charges to other items lines on the transaction if needed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Użytkownik może powtórzyć ten proces, aby dodać opłaty dodatkowe na poziomie wiersza do innych wierszy towarów w ramach transakcji, jeśli jest taka potrzeba.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>The same process can be applied in the call center by using the "maintain charges" feature found under the <bpt id="p1">**</bpt>Financials<ept id="p1">**</ept> drop-down menu in the <bpt id="p2">**</bpt>Sales order lines<ept id="p2">**</ept> section on the <bpt id="p3">**</bpt>Sales order<ept id="p3">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ten sam proces można zastosować w biurze obsługi za pomocą funkcji „Obsługa opłat” dostępnych na liście menu rozwijanego <bpt id="p1">**</bpt>Finanse<ept id="p1">**</ept> w sekcji <bpt id="p2">**</bpt>Wiersze zamówienia sprzedaży<ept id="p2">**</ept> na stronie <bpt id="p3">**</bpt>Zamówienie sprzedaży<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>This will open the <bpt id="p1">**</bpt>Maintain charges<ept id="p1">**</ept> page where the user can add a new line specific charge to the transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Spowoduje to otwarcie strony <bpt id="p1">**</bpt>Obsługa opłat<ept id="p1">**</ept>, na której użytkownik może dodać do transakcji nową opłatę specyficzną dla wiersza.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>Additional features</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dodatkowe funkcje</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>Editing charges on a POS sales transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Edytowanie opłat na transakcji sprzedaży POS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>The <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation (142) should be added to the <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a user can view and edit or override any system-calculated or manually-created header or line-level charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Operacja <bpt id="p1">**</bpt>Zarządzaj opłatami dodatkowymi<ept id="p1">**</ept> (142) powinna zostać dodana do <bpt id="p2">[</bpt>układu ekranu POS<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept>, aby umożliwić wyświetlanie i edytowanie lub zastępowanie wszelkich opłat na poziomie nagłówka lub wiersza obliczanych przez system lub ręcznie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>If the operation is not added, users will not be able to adjust the value of the charges on the POS transaction, nor will they be able to view the details of the charges such as the type of charges code tied to the charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli operacja nie zostanie dodana, użytkownicy nie będą mogli zmienić wartości opłat w transakcji POS ani wyświetlać szczegółów opłat, takich jak typ kodu opłaty powiązany z opłatą.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source>On the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> page in POS, the user can view both header and line-level charges details.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Zarządzaj opłatami dodatkowymi<ept id="p1">**</ept> w POS użytkownik może wyświetlić zarówno nagłówek, jak i szczegóły opłaty na poziomie wiersza.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>The user can use the <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept> function available on this page to make changes to the amount charged to a specific charges line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Użytkownik może użyć funkcji <bpt id="p1">**</bpt>Edytuj<ept id="p1">**</ept> na tej stronie, aby wprowadzić zmiany do kwoty pobieranej z konkretnego wiersza opłat.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>Once a charges line is overwritten manually, it will not be systematically recalculated unless the user initiates the <bpt id="p1">**</bpt>Recalculate charges<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po ręcznym nadpisaniu wiersza opłat nie będzie on systemowo obliczany ponownie, chyba że użytkownik zainicjuje operację <bpt id="p1">**</bpt>Ponownie oblicz opłaty<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>If the <bpt id="p1">**</bpt>Charge override reason code<ept id="p1">**</ept> has been configured on the <bpt id="p2">**</bpt>Retail parameters<ept id="p2">**</ept> setup page, the user will be prompted to provide a reason code when charges have been modified in the POS application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli <bpt id="p1">**</bpt>Kod przyczyny zastąpienia opłat<ept id="p1">**</ept> został skonfigurowane na stronie konfiguracji <bpt id="p2">**</bpt>Parametry sieci sprzedaży<ept id="p2">**</ept>, użytkownik będzie monitowany o podanie kodu przyczyny, kiedy opłaty są modyfikowane w aplikacji POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>If reason codes have been captured for overwritten charges, a new report is also available to review and audit these overrides.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli kod przyczyny został zarejestrowany dla nadpisanych opłat, nowy raport również jest dostępny do sprawdzenia i kontroli tych nadpisań.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>The report can be found in <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Inquiries and reports <ph id="ph2">\&gt;</ph> Charge override history<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Raport można znaleźć w menu <bpt id="p1">**</bpt>Handel detaliczny <ph id="ph1">\&gt;</ph> Zapytania i raporty <ph id="ph2">\&gt;</ph> Historia zastąpień opłat<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source>Refunding charges on a POS return transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zwracanie opłat w ramach transakcji zwrotu POS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source>If the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is set to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>, the existing retail parameter for <bpt id="p3">**</bpt>Refund shipping charges<ept id="p3">**</ept> is no longer applicable.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli parametr <bpt id="p1">**</bpt>Użyj zaawansowanego automatycznego naliczania opłat dodatkowych<ept id="p1">**</ept> jest ustawiony na <bpt id="p2">**</bpt>Tak<ept id="p2">**</ept>, istniejący parametr sieci sprzedaży dla <bpt id="p3">**</bpt>Zwróć opłaty transportowe<ept id="p3">**</ept> nie ma już zastosowania.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="244">
          <source>To indicate which charges should be systematically refunded to a customer when using advanced auto-charges, ensure the related charges code has been configured as <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> setup page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby wskazać, które opłaty mają być systemowo zwracane odbiorcy w kontekście zaawansowanych automatycznych opłat dodatkowych, należy upewnić się, że odpowiedni kod opłat został skonfigurowany jako <bpt id="p1">**</bpt>Zwrot<ept id="p1">**</ept> na stronie konfiguracji <bpt id="p2">**</bpt>Kod opłat<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="245">
          <source>Make sure that the settings have been synchronized to your Retail channel databases through distribution schedule processing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Upewnij się, że ustawienia zostały zsynchronizowane z bazami danych kanału sprzedaży detalicznej za pomocą przetwarzania harmonogramu dystrybucji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="246">
          <source>Refunding charges on a return order transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zwracanie opłat w ramach transakcji zamówienia</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="247">
          <source>Charges are not systematically refunded to <bpt id="p1">**</bpt>Return orders<ept id="p1">**</ept> created in Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Opłaty nie są systemowo zwracane do <bpt id="p1">**</bpt>Zamówień zwrotu<ept id="p1">**</ept> utworzonych w sieci sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="248">
          <source>Users are required to select the <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> option when creating the <bpt id="p2">**</bpt>Return order<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Użytkownicy muszą wybrać opcję <bpt id="p1">**</bpt>Kopiuj opłaty<ept id="p1">**</ept> podczas tworzenia <bpt id="p2">**</bpt>Zamówienia zwrotu<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="249">
          <source>If <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> is not selected, charges from the original sales transaction will not be automatically refunded.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli opcja <bpt id="p1">**</bpt>Kopiuj opłaty<ept id="p1">**</ept> jest została zaznaczona, opłaty z pierwotnej transakcji sprzedaży nie zostaną automatycznie zwrócone.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="250">
          <source>If <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> is selected, all charges will be copied to the return order and the user can manually edit or remove any charges they do not want to have refunded.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli opcja <bpt id="p1">**</bpt>Kopiuj opłaty<ept id="p1">**</ept> jest zaznaczona, wszystkie opłaty zostaną skopiowane do zamówienia zwrotu, a użytkownik może ręcznie edytować lub usunąć wszelkie opłaty, które nie mają zostać zwrócone.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="251">
          <source>The call center return order process currently does not acknowledge the <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Proces zamówienia zwroty z biura obsługi obecnie nie zatwierdza flagi <bpt id="p1">**</bpt>Zwrot<ept id="p1">**</ept> w konfiguracji <bpt id="p2">**</bpt>Kod opłat<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="252">
          <source>Configuring POS receipts to show charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie przyjęć POS, aby pokazywały opłaty</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="253">
          <source>The following receipt elements have been added to the receipt line and footer to support the advanced auto-charges functionality.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Dodano następujące elementy przyjęcia do wiersza przyjęcia i stopki do obsługi funkcji zaawansowanych automatycznych opłat dodatkowych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="254">
          <source><bpt id="p1">**</bpt>Line Shipping Charges<ept id="p1">**</ept> – This line-level element can be used to recap specific charges codes that have been applied to the sales line.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Opłaty transportowe w wierszach<ept id="p1">**</ept> — ten element poziomu wiersza może służyć do podsumowania określonych kodów opłat, które zostały zastosowane do wiersza sprzedaży.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="255">
          <source>Only charges codes that have been flagged as <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> charges on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> page will be displayed here.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Tylko kody opłat, które zostały oflagowane jako opłaty <bpt id="p1">**</bpt>Transportowe<ept id="p1">**</ept> na stronie <bpt id="p2">**</bpt>Kod opłat<ept id="p2">**</ept> zostaną tutaj wyświetlone.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="256">
          <source><bpt id="p1">**</bpt>Line Other Charges<ept id="p1">**</ept> – This line-level element can be used to recap any non-shipping specific charge codes that have been applied to the sales line.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Inne opłaty w wierszach<ept id="p1">**</ept> — ten element poziomu wiersza może służyć do podsumowania wszelkich kodów opłat niezwiązanych z wysyłką, które zostały zastosowane do wiersza sprzedaży.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="257">
          <source>These are charges codes where the <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> flag on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> page has not been enabled.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Są to kody opłat, dla których flaga <bpt id="p1">**</bpt>Transportowe<ept id="p1">**</ept> na stronie <bpt id="p2">**</bpt>Kod opłat<ept id="p2">**</ept> nie została włączona.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="258">
          <source><bpt id="p1">**</bpt>Order Shipping Charges Details<ept id="p1">**</ept> – This footer-level element displays the descriptions of the charge codes applied to the order that have been flagged as <bpt id="p2">**</bpt>Shipping<ept id="p2">**</ept> charges on the <bpt id="p3">**</bpt>Charges code<ept id="p3">**</ept> setup page.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Szczegóły opłat transportowych w zamówieniach<ept id="p1">**</ept> — ten element poziomu stopki wyświetla opisy kodów opłat stosowanych do zamówienia, które zostało oflagowane jako opłaty <bpt id="p2">**</bpt>Transportowe<ept id="p2">**</ept> na stronie <bpt id="p3">**</bpt>Kody opłat<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="259">
          <source><bpt id="p1">**</bpt>Order Shipping Charges<ept id="p1">**</ept> – This footer-level element shows the dollar value of the shipping-related charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Opłaty transportowe w zamówieniach<ept id="p1">**</ept> — ten element poziomu stopki pokazuje wartość w dolarach opłat związanych z wysyłką.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="260">
          <source><bpt id="p1">**</bpt>Order Other Charges Details<ept id="p1">**</ept> – This footer-level element displays the description of the charges codes applied to the order that have not been flagged as shipping-related charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Szczegóły innych opłat w zamówieniach<ept id="p1">**</ept> — ten element poziomu stopki wyświetla opis kodów opłat stosowanych do zamówienia, które nie zostało oflagowane jako związane z opłatami transportowymi.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="261">
          <source><bpt id="p1">**</bpt>Order Other Charges<ept id="p1">**</ept> – This footer-level element displays the dollar value of the other charges that are not shipping-related.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Inne opłaty w zamówieniach<ept id="p1">**</ept> — ten element poziomu stopki wyświetla wartość w dolarach innych opłat, które nie są związane z wysyłką.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="262">
          <source>It is recommended that the organization also add free text fields to the receipt footer, in order to define the areas where charges will be recapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zalecane jest, aby organizacja także dodała pola dowolnego tekstu do stopki przyjęcia, aby zdefiniować obszary, w których opłaty będą podsumowywane.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="263">
          <source>Preventing charges from being calculated until the POS order is completed</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Uniemożliwienie obliczania opłat aż do zamknięcia zamówienia POS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="264">
          <source>Some organizations may prefer to wait until the user has finished adding all of the sales lines to the POS transaction before calculating charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Niektóre organizacje mogą woleć czekać, aż użytkownik zakończy dodawanie wszystkich wierszy sprzedaży do transakcji POS przed obliczeniem opłat.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="265">
          <source>To prevent calculation of charges as items are added to the POS transaction, turn on the <bpt id="p1">**</bpt>Manual charge calculation<ept id="p1">**</ept> parameter in the <bpt id="p2">**</bpt>Functionality profile<ept id="p2">**</ept> used by the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby zapobiec obliczaniu opłat w trakcie dodawania pozycji do transakcji POS, włącz parametr <bpt id="p1">**</bpt>Ręczne obliczanie opłat<ept id="p1">**</ept> w <bpt id="p2">**</bpt>Profilu funkcjonalnym<ept id="p2">**</ept> używanym w danym sklepie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="266">
          <source>Enabling this parameter will require the POS user to use the <bpt id="p1">**</bpt>Calculate totals<ept id="p1">**</ept> operation when they have completed adding the products to the POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Włączenie tego parametru będzie wymagać od użytkownika POS użycia operacji <bpt id="p1">**</bpt>Oblicz sumy<ept id="p1">**</ept> po zakończeniu dodawania produktów do transakcji POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="267">
          <source>The <bpt id="p1">**</bpt>Calculate totals<ept id="p1">**</ept> operation will then trigger the calculation of any auto charges for the order header or lines as applicable.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Operacja <bpt id="p1">**</bpt>Oblicz sumy<ept id="p1">**</ept> spowoduje następnie obliczenie wszelkich automatycznych opłat dodatkowych dla nagłówka lub wierszy zamówienia, stosownie do przypadku.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="268">
          <source>Charges override reports</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Raporty zastępowania opłat</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="269">
          <source>If users manually override the calculated charges or add a manual charge to the transaction, this data will available for auditing in the <bpt id="p1">**</bpt>Charge Override History<ept id="p1">**</ept> report.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli użytkownik ręcznie zastąpi obliczone opłaty lub doda ręcznie opłatę do transakcji, te dane będą dostępne na potrzeby audytu w raporcie <bpt id="p1">**</bpt>Historia zastąpień opłat<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="270">
          <source>The report can be accessed from <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Inquiries and reports <ph id="ph2">\&gt;</ph> Charge Override History<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Raport można znaleźć w menu <bpt id="p1">**</bpt>Handel detaliczny <ph id="ph1">\&gt;</ph> Zapytania i raporty <ph id="ph2">\&gt;</ph> Historia zastąpień opłat<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="271">
          <source>It is important to note that the data needed for this report is imported from the channel database into HQ through the "P" distribution schedule jobs.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Należy pamiętać, że dane potrzebne dla tego raportu będą importowane z bazy danych kanałów do Centrali za pośrednictwem zadań harmonogramu dystrybucji „P”.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="272">
          <source>Therefore, information about overrides just performed in the POS may not be immediately available on this report until this job has uploaded the store transaction data into HQ.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W związku z tym informacje o zastąpieniach właśnie wprowadzonych w punkcie sprzedaży mogą nie być natychmiast dostępne w tym raporcie, chyba że to zadanie przesłało dane o transakcjach w sklepie do centrali.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>