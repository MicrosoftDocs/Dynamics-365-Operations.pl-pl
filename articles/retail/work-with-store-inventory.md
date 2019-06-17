<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="work-with-store-inventory.md" target-language="pl-PL">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>work-with-store-inventory.418f90.551a8408aa730bc1916f1c57b7cfd773966ce8bf.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>551a8408aa730bc1916f1c57b7cfd773966ce8bf</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>e2fb0846fcc6298050a0ec82c302e5eb5254e0b5</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/27/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\work-with-store-inventory.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Store inventory management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zarządzanie zapasami w sklepie</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes the types of documents that you can use to manage inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym temacie opisano typy dokumentów, których można używać do zarządzania zapasami.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Store inventory management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zarządzanie zapasami w sklepie</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>When working with inventory in Dynamics 365 for Retail and using the POS application, it is important to note that POS provides limited support for inventory dimensions and certain inventory item types.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Podczas pracy z zapasami w programie Dynamics 365 for Retail i używania aplikacji POS należy zwrócić uwagę, że POS zapewnia ograniczoną obsługę wymiarów magazynowych i zapasów określonych typów towarów.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>The POS solution does not support the following item configurations:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rozwiązanie POS nie obsługuje następujących konfiguracje towarów:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>BOM items (except kit products, which utilize some components of the BOM framework)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Towary BOM (z wyjątkiem zestawów wykorzystujących komponenty struktury BOM)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Catch weight items</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Towary w ilości efektywnej</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Batch-controlled items</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Towary wchodzące w skład partii</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>The POS application currently does not support the following tracking dimensions in the POS:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aplikacja POS aktualnie nie obsługuje następujących wymiarów śledzenia w POS:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Batch tracking dimension</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wymiar śledzenia partii</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Owner dimension</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wymiar właściciela</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>The POS solution provides limited support for the following dimensions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rozwiązanie POS zapewnia ograniczoną obsługę następujących wymiarów.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Limited support indicates that the POS may default some of these dimensions into inventory transactions automatically based on warehouse/store setup configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ograniczona obsługa oznacza, że POS może w sposób automatyczny domyślnie używać niektórych z tych wymiarów w transakcjach zapasów na podstawie konfiguracji magazynu/sklepu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>POS will not fully support the dimensions in the way they are supported if a sales transaction is manually entered into the ERP.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">POS nie obsługuje w pełni wymiarów w sposób, w jaki są one obsługiwane, jeśli transakcja sprzedaży jest ręcznie wprowadzana do systemu ERP.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source><bpt id="p1">**</bpt>Warehouse Location<ept id="p1">**</ept> – Users will not have the ability to manage the receiving warehouse location for items received into a store warehouse when the store has not been configured to use the warehouse management process.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Lokalizacja magazynu<ept id="p1">**</ept> — użytkownicy nie będą mieli możliwości zarządzania lokalizacją magazynu przyjmującego dla towarów otrzymanych w magazynie sklepu, jeśli sklep nie został skonfigurowany pod kątem korzystania z procesu zarządzania magazynem.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>A default receiving location defined on the store warehouse will be used for these items.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dla tych towarów będą używane domyślne lokalizacje przyjęcia zdefiniowane w magazynie sklepu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>If the warehouse management process has been enabled for the store, limited support that prompts the user to choose a receiving location for the entire receipt will be triggered.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli dla sklepu został włączony proces zarządzania magazynem, zostanie wyzwolony monit o wybranie lokalizacji odbierającej dla całego paragonu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Items sold from the store will always be sold out of the default retail location as defined on the store warehouse setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Towary sprzedane ze sklepu będą zawsze sprzedawane poza domyślną lokalizacją sprzedaży detalicznej zgodnie z ustawieniami magazynu sklepu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>The location for managing return inventory can be controlled through default return location definition on the store warehouse or based on return reason codes as defined in the return location policy.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Lokalizacja zarządzania zapasami zwrotu może być kontrolowana za pośrednictwem domyślnej definicji lokalizacji zwrotu w magazynie sklepu lub na podstawie kodów przyczyn zwrotu, zgodnie z zasadami lokalizacji zwrotu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source><bpt id="p1">**</bpt>License plate<ept id="p1">**</ept> – License plates are only applicable when <bpt id="p2">**</bpt>Use warehouse management process<ept id="p2">**</ept> has been enabled on the item and the store warehouse.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Numer identyfikacyjny<ept id="p1">**</ept> — stosowany tylko po włączeniu opcji <bpt id="p2">**</bpt>Używaj procesu zarządzania magazynem<ept id="p2">**</ept> dla towaru i magazynu sklepu.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>In POS, if inventory is received into a store warehouse where the warehouse management process has been enabled, and the location chosen to receive the item into is tied to a location profile that requires license plate control, the POS application will systematically apply a license plate to the receiving line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W punkcie sprzedaży, w przypadku przyjęcia zapasów do magazynu sklepu, w którym został włączony proces zarządzania magazynem, a lokalizacja wybrana do odebrania towaru jest powiązana z profilem lokalizacji, który wymaga kontroli numeru identyfikacyjnego, aplikacja punktu sprzedaży będzie systematycznie stosować numer identyfikacyjny do wiersza przyjęcia.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Users in POS will not have the ability to change or manage this license plate data.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Użytkownicy w punkcie sprzedaży nie będą mieli możliwości zmiany tego numeru identyfikacyjnego ani zarządzania nim.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>If full management of license plates is required, it is suggested the store use the WMS mobile application or the back office ERP client to manage the receipt of these items.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Jeśli wymagane jest pełne zarządzanie numerami identyfikacyjnymi, zaleca się, aby w sklepie można było zarządzać odbiorem tych towarów za pomocą aplikacji mobilnej WMS lub klienta zaplecza Office ERP</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source><bpt id="p1">**</bpt>Serial number<ept id="p1">**</ept> – The POS application has limited support for single serial number to be registered on a transaction sales line for orders created in POS with serialized items.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Numer seryjny<ept id="p1">**</ept> — aplikacja punktu sprzedaży ma ograniczone funkcje obsługi dla pojedynczego numeru seryjnego, który ma być zarejestrowany w wierszu sprzedaży transakcji dla zamówień utworzonych w punkcie sprzedaży z towarami seryjnymi.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>This serial number is not validated against registered serial numbers already in inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ten numer seryjny nie jest sprawdzany względem zarejestrowanych numerów seryjnych, które już są w magazynie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>If a sales order is created in the call center channel or fulfilled through the ERP and multiple serial numbers are registered to a single sales line during the fulfillment process in the ERP, these serial numbers will not be able to be applied or validated if a return is processed in POS for these orders.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Jeśli zamówienie sprzedaży jest tworzone w kanale biura obsługi lub realizowane za pośrednictwem systemu ERP, a wiele numerów seryjnych jest zarejestrowanych w jednym wierszu sprzedaży w trakcie procesu realizacji w systemie ERP, te numery seryjne nie będą mogły zostać zastosowane ani sprawdzone, jeśli zwrot ma wartość „przetworzono” w punkcie sprzedaży dla tych zamówień.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source><bpt id="p1">**</bpt>Inventory status<ept id="p1">**</ept> – For items that use the warehouse management process and require an inventory status, this status field is not able to be set or modified through the POS application.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Stan zapasów<ept id="p1">**</ept> — w przypadku towarów, które korzystają z procesu zarządzania magazynem i wymagają stanu zapasów, to pole stanu nie może być konfigurowane ani modyfikowane za pośrednictwem aplikacji punktu sprzedaży.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>The default inventory status as defined on the store warehouse configuration will be used when items are received into inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Domyślny stan zapasów określony w konfiguracji magazynu sklepu będzie używany podczas przyjęcia towarów do magazynu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>All organizations must test item configurations through POS in development or test environments before deploying them to production.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wszystkie organizacje muszą przetestować konfiguracje towarów za pomocą POS w środowiskach rozwojowych lub testowych przed ich wdrożeniem do produkcji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>Test your items by performing regular cash and carry sales transacting and creating customer orders (if applicable) through the POS with your items.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Należy przetestować towary, wykonując zwykłą sprzedaż kasową i tworząc zamówienia odbiorcy (jeśli dotyczy) za pomocą POS z Twoimi towarami.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Testing must include running a full statement posting processes in your test environment and verifying that there are no issues.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Testowanie musi obejmować procesy księgowania pełnych zestawień w środowisku testowym i sprawdzenie, że nie ma problemów.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Configuring items in a way that is not supported by the POS application, without proper testing, can result in your statement posting process failing in production without an easy way to correct the issues.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie towarów w sposób, który nie jest obsługiwany przez aplikację POS, bez odpowiedniego przetestowania, może doprowadzić do błędu przetwarzania księgowania zestawienia w produkcji, którego nie będzie można łatwo naprawić.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>Partner or customer customizations to the application may optionally be considered to allow these posting processes to successfully complete.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zmiany wprowadzone w aplikacji przez partnera lub klienta mogą opcjonalnie zezwalać na pomyślne realizowanie tych procesów księgowania.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>If customizations are not needed, the organization must ensure that the product configuration of your products has been done in a way that is supported by the standard POS application/order creation/statement posting process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli dostosowania nie są potrzebne, organizacja musi upewnić się, że konfiguracja produktu została wykonane w sposób, który jest obsługiwany przez standardowe proces aplikacji POS/tworzenia zamówień/księgowania zestawień.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>Purchase orders</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zamówienia zakupu</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>Purchase orders are created at the head office.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zamówienia zakupu są tworzone w centrali.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>If a retail warehouse is included in the purchase order header, the order can be received at the store by using Modern POS (MPOS) or Cloud POS in Microsoft Dynamics 365 for Retail through the <bpt id="p1">**</bpt>Picking/Receiving<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli magazyn sprzedaży detalicznej znajduje się w nagłówku zamówienia zakupu, zamówienia można otrzymać w sklepie przy użyciu aplikacji Modern POS (MPOS) lub Cloud POS dostępnej w programie Microsoft Dynamics 365 for Retail, korzystając z operacji <bpt id="p1">**</bpt>pobrania/przyjęcia<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>After the quantities that are received at the store are entered in the <bpt id="p1">**</bpt>Receive Now<ept id="p1">**</ept> field in POS for the purchase order document, they can be saved locally or committed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po wprowadzeniu ilości odebranych w sklepie w polu <bpt id="p1">**</bpt>Dostarczone teraz<ept id="p1">**</ept> w punkcie sprzedaży dla dokumentu zamówienia zakupu, można je zapisać lokalnie lub zatwierdzić.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Saving this data locally has no effect on in-stock inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zapisanie tych danych lokalnie nie ma wpływu na zapasy w magazynie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Saving should be done only if the user is not ready to post the receipt to HQ and just needs a way to temporarily store the previously entered <bpt id="p1">**</bpt>Receive Now<ept id="p1">**</ept> data.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zapisywanie powinno być wykonywane tylko wtedy, gdy użytkownik nie jest gotowy do zaksięgowania przyjęcia w centrali i musi mieć możliwość tymczasowego przechowywania poprzednio wprowadzonych danych towaru <bpt id="p1">**</bpt>dostarczonego teraz<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>This saves the receive now data locally to the user's channel database.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Spowoduje to zapisanie lokalne danych towaru dostarczonego teraz w bazie danych kanału użytkownika.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>After the document is processed using the <bpt id="p1">**</bpt>Commit<ept id="p1">**</ept> option, the <bpt id="p2">**</bpt>Receive Now<ept id="p2">**</ept> data is sent to HQ and the purchase order receipt will be posted.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po przetworzeniu dokumentu przy użyciu opcji <bpt id="p1">**</bpt>zatwierdzania<ept id="p1">**</ept> dane towaru <bpt id="p2">**</bpt>dostarczonego teraz<ept id="p2">**</ept> są wysyłane do centrali i zostanie zaksięgowany paragon zamówienia zakupu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>Transfer orders</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zamówienia przeniesienia</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>A transfer order can specify that a particular store is the location that items can be shipped from or the location the inventory will be received into.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zamówienie przeniesienia może określać, czy dany sklep jest lokalizacją, z której można wysyłać towary, czy też lokalizacją, w której zostaną odebrane zapasy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>If the POS user is the shipping warehouse for a transfer order, they will be able to enter <bpt id="p1">**</bpt>Ship Now<ept id="p1">**</ept> quantities from POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli użytkownik punktu sprzedaży jest magazynem wysyłkowym dla zamówienia przeniesienia, będzie mógł wprowadzać ilości <bpt id="p1">**</bpt>wysyłki teraz<ept id="p1">**</ept> z punktu sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>The data entered by the shipping store can be saved locally or committed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dane wprowadzone przez sklep wysyłkowy mogą być zapisywane lokalnie lub zatwierdzane.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>When saved locally, no updates are made to the transfer order document in HQ.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W przypadku zapisania danych lokalnie nie są wprowadzane żadne aktualizacje dokumentu zamówienia przeniesienia w centrali.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>Saving should be done only if the user is not ready to post the shipment to HQ and needs a way to temporarily store the previously entered <bpt id="p1">**</bpt>Ship Now<ept id="p1">**</ept> data.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zapisywanie powinno być wykonywane tylko wtedy, gdy użytkownik nie jest gotowy do zaksięgowania wysyłki w centrali i musi mieć możliwość tymczasowego przechowywania poprzednio wprowadzonych danych towaru <bpt id="p1">**</bpt>wysłanego teraz<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>After the store is ready to confirm shipment, the <bpt id="p1">**</bpt>Commit<ept id="p1">**</ept> option should be selected.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gdy sklep będzie gotowy do potwierdzenia wysyłki, należy wybrać opcję <bpt id="p1">**</bpt>Zatwierdź<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>This posts the shipment of the transfer order in HQ so that the receiving warehouse will now be able to receive against it.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Spowoduje to zaksięgowanie wysyłki zamówienia przeniesienia w centrali, dzięki czemu magazyn odbierający będzie miał teraz możliwość otrzymywania towaru na podstawie tego dokumentu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>If the POS user is the receiving warehouse for a transfer order, they will be able to enter the <bpt id="p1">**</bpt>Receive Now<ept id="p1">**</ept> quantities from POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli użytkownik punktu sprzedaży jest magazynem odbierającym dla zamówienia przeniesienia, będzie mógł wprowadzać ilości <bpt id="p1">**</bpt>dostarczone teraz<ept id="p1">**</ept> z punktu sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>The data entered by the receiving store can be saved locally or committed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dane wprowadzone przez sklep odbierający mogą być zapisywane lokalnie lub zatwierdzane.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>Saving should be done only if the user is not ready to post the receipt to HQ and needs a way to temporarily store the previously entered <bpt id="p1">**</bpt>Receive Now<ept id="p1">**</ept> data.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zapisywanie powinno być wykonywane tylko wtedy, gdy użytkownik nie jest gotowy do zaksięgowania przyjęcia w centrali i musi mieć możliwość tymczasowego przechowywania poprzednio wprowadzonych danych towaru <bpt id="p1">**</bpt>dostarczonego teraz<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>This saves the receive now data locally to the user's channel database.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Spowoduje to zapisanie lokalne danych towaru dostarczonego teraz w bazie danych kanału użytkownika.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>After the document is processed using the <bpt id="p1">**</bpt>Commit<ept id="p1">**</ept> option, the <bpt id="p2">**</bpt>Receive Now<ept id="p2">**</ept> data is sent to HQ and the transfer order receipt will be posted.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po przetworzeniu dokumentu przy użyciu opcji <bpt id="p1">**</bpt>zatwierdzania<ept id="p1">**</ept> dane towaru <bpt id="p2">**</bpt>dostarczonego teraz<ept id="p2">**</ept> są wysyłane do centrali i zostanie zaksięgowany paragon zamówienia przeniesienia.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>It's important to note that the receiving store will be restricted to only being able to commit receive quantities that are equal to or less than shipped quantities.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Należy pamiętać, że sklep odbierający będzie mógł odebrać ilość mniejszą lub równą wysłanej ilości.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>An attempt to receive quantities on a transfer order that have not previously shipped will result in errors and the receipt will not be confirmed in HQ.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Próba odbioru ilości z zamówienia przeniesienia, które nie zostały wysłane, spowoduje wyświetlenie komunikatu o błędzie, a paragon nie zostanie potwierdzony w centrali.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Stock counts</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Stany zapasów z inwentaryzacji</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Stock counts can be either scheduled or unscheduled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inwentaryzacje mogą być zaplanowane lub niezaplanowane.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Scheduled stock counts are initiated at the head office, which specifies the items that must be counted.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zaplanowana inwentaryzacja jest inicjowana z poziomu centrali, która określa towary podlegające inwentaryzacji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>The head office creates a counting document that can be received at the store, where the quantities of actual on-hand stock are entered in MPOS or Cloud POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Centrala tworzy dokument inwentaryzacji, który można otrzymać w sklepie. Rzeczywista ilość dostępnych zapasów jest wprowadzana w aplikacji MPOS lub Cloud POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>Unscheduled stock counts are initiated at a store, and the quantities of actual on-hand stock are updated in either MPOS or Cloud POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Niezaplanowane inwentaryzacje są inicjowane w sklepie, a rzeczywista ilość dostępnych zapasów jest aktualizowana w aplikacji MPOS lub Cloud POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>Unlike scheduled stock counts, unscheduled stock counts do not have a predefined list of items.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W odróżnieniu od zaplanowanej inwentaryzacji niezaplanowana nie ma wstępnie zdefiniowanej listy pozycji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>When a stock count of either type is completed, it is committed and sent to the head office.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po zakończeniu inwentaryzacja dowolnego typu jest zatwierdzana wysyłana do centrali.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>At the head office, the count is validated and posted as a separate step.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W centrali dane podlegają sprawdzeniu i zaksięgowaniu w ramach osobnej procedury.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Inventory lookup</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wyszukiwanie w magazynie</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>The current product quantity on hand for multiple stores and warehouses can be viewed on the <bpt id="p1">**</bpt>Inventory lookup<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Bieżącą ilość produktów dostępnych w wielu sklepach i magazynach można obejrzeć na stronie <bpt id="p1">**</bpt>Wyszukiwanie w magazynie<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>In addition to the current quantity on hand, the future available to promise (ATP) quantities can be viewed for each individual store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Oprócz bieżącej ilości dostępnej w zapasach można wyświetlić przyszłe dostępności zapasów (ATP) dla poszczególnych sklepów.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>To do so, select the store that you want to view the ATP for and then click <bpt id="p1">**</bpt>Show store availability<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby to zrobić, zaznacz sklep, dla którego chcesz obejrzeć ATP, i kliknij przycisk <bpt id="p1">**</bpt>Pokaż dostępność sklepu<ept id="p1">**</ept>.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>