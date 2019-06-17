<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="set-up-external-catalog-for-punchout.md" target-language="pl-PL">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>set-up-external-catalog-for-punchout.474d96.39baa331120d765543c3cf662ce53d2bcfe404ab.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>39baa331120d765543c3cf662ce53d2bcfe404ab</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>574d4dda83dcab94728a3d35fc53ee7e2b90feb0</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/22/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\supply-chain\procurement\set-up-external-catalog-for-punchout.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Set up an external catalog for PunchOut eProcurement</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie katalogu zewnętrznego dla rozwiązania PunchOut eProcurement</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes the use of an  external catalog or punchout catalog to collect quote information from a vendor and add it to a requisition.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym temacie opisano używanie zewnętrznego katalogu (dynamicznie dostępnego katalogu dostawcy, punchout) w celu zbierania informacji ofertowych od dostawcy i dodawania ich do zapotrzebowania.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Set up an external catalog for PunchOut eProcurement</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie katalogu zewnętrznego dla rozwiązania PunchOut eProcurement</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>By using the external catalog, you can ensure that the product and price information that you subsequently process in Dynamics 365 for Finance and Operations July 2017 is accurate and up to date.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Używając zewnętrznego katalogu, można mieć pewność, że informacje o produktach i cenach, które następnie będą przetwarzane w programie Dynamics 365 for Finance and Operations w wersji z lipca 2017 roku, są dokładne i aktualne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>The requisition can then be approved and converted to a purchase order and an order can be placed at the vendor.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zapotrzebowanie można następnie zatwierdzić i przekonwertować na zamówienie zakupu, które zostanie złożone u dostawcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>When the external catalog is set up and an employee is preparing a requisition, there will be an option to redirect to an external site, the external catalog, and return the shopping basket that was created at the external site.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po skonfigurowaniu zewnętrznego katalogu pracownik przygotowujący zapotrzebowanie będzie miał możliwość przejścia do zewnętrznej witryny (zewnętrznego katalogu), a następnie zwrócenia z niej koszyka zakupów do swojej macierzystej witryny.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>This communication is based on the cXML protocol and it has to be set up between the systems of the buying and the selling organization.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ta komunikacja opiera się na protokole cXML i musi być skonfigurowana między systemami organizacji kupującej i sprzedającej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>To set up the communication, your vendor has to provide pieces of information for you to use in the configuraiton of the external catalog such as Identity, domain of the buyers company, for example, "DUNS" and "DUNS number", credentials, and the URL to reach the vendors catalog.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby można było skonfigurować taką komunikację, dostawca musi podać elementy informacji, których będziesz używać w konfiguracji zewnętrznego katalogu, takie jak tożsamość, domena firmy nabywcy (na przykład „DUNS” i „Numer DUNS”), poświadczenia oraz adres URL, pod którym jest dostępny katalog dostawcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Setting up an external catalog</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie zewnętrznego katalogu</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>The external catalog should enable an employee who enters a purchase requisition to be redirected to an external site to select products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zewnętrzny katalog powinien umożliwiać pracownikowi wprowadzającemu zapotrzebowanie na zakup przejście do zewnętrznej witryny w celu wybrania produktów.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The products that the employee selects from the external catalog are returned to Dynamics 365 for Finance and Operations with up-to-date price information and from here, they can be added to the purchase requisition.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Produkty wybrane przez pracownika z zewnętrznego katalogu są zwracane do programu Dynamics 365 for Finance and Operations z aktualnymi informacjami cenowymi i z tego miejsca mogą zostać dodane do zapotrzebowania na zakup.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>The intention is not to enable employees to place an order on the external site.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Celem nie jest umożliwienie pracownikom składania zamówień bezpośrednio w zewnętrznej witrynie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>When setting up the external catalog, you need to make sure that the purpose of the site that can be accessed by the external catalog is to collect quote information and not to place a real order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Podczas konfigurowania zewnętrznego katalogu należy upewnić się, że celem witryny dostępnej przez zewnętrzny katalog jest tylko zebranie informacji ofertowych, a nie złożenie faktycznego zamówienia.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>To set up an external vendor catalog, complete the following tasks:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby skonfigurować zewnętrzny katalog dostawcy, należy wykonać następujące zadania:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Set up a procurement category hierarchy.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ustawianie hierarchii kategorii zaopatrzenia.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>For more information, see <bpt id="p1">[</bpt>Set up policies for procurement category hierarchies<ept id="p1">](tasks/set-up-policies-procurement-category-hierarchies.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby uzyskać więcej informacji, zobacz <bpt id="p1">[</bpt>Konfigurowanie zasad dla hierarchii kategorii zaopatrzenia<ept id="p1">](tasks/set-up-policies-procurement-category-hierarchies.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Register the vendor in Finance and Operations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zarejestrowanie dostawcy w programie Finance and Operations.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Before you can set up configurations to access an external vendor’s catalog, you must set up the vendor and the vendor contact in Microsoft Dynamics 365.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby można było utworzyć konfiguracje pozwalające na dostęp do zewnętrznego katalogu dostawcy, należy skonfigurować dostawcę i jego osobę kontaktową w programie Microsoft Dynamics 365.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>The external catalog’s vendor must also be added to the selected procurement category.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ponadto dostawca zewnętrznego katalogu musi być dodany do wybranej kategorii zaopatrzenia.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>For more information about registering vendors in Microsoft Dynamics 365, see <bpt id="p1">[</bpt>Manage vendor collaboration users<ept id="p1">](manage-vendor-collaboration-users.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby uzyskać więcej informacji o rejestrowaniu dostawców w programie Microsoft Dynamics 365, zobacz <bpt id="p1">[</bpt>Zarządzanie użytkownikami modułu Współpraca z dostawcami<ept id="p1">](manage-vendor-collaboration-users.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>For information about how to assign vendors to a procurement category, see <bpt id="p1">[</bpt>Approve vendors for specific procurement categories<ept id="p1">](tasks/approve-vendors-specific-procurement-categories.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby uzyskać informacje o przypisywaniu dostawców do kategorii zaopatrzenia, zobacz <bpt id="p1">[</bpt>Zatwierdzanie dostawców dla konkretnych kategorii zaopatrzenia<ept id="p1">](tasks/approve-vendors-specific-procurement-categories.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Make sure that the units of measure and the currency that the vendor uses are set up.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skonfigurowanie jednostek miary i waluty używanych przez dostawcę.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>For information about how to create a unit of measure, see <bpt id="p1">[</bpt>Manage units of measure<ept id="p1">](../pim/tasks/manage-unit-measure.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby uzyskać informacje o tworzeniu jednostki miary, zobacz <bpt id="p1">[</bpt>Zarządzanie jednostkami miary<ept id="p1">](../pim/tasks/manage-unit-measure.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Configure the external vendor catalog by using the requirements for your vendor’s external catalog site.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skonfigurowanie zewnętrznego katalogu dostawcy z uwzględnieniem wymagań obowiązujących w witrynie tego katalogu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>For more details about this task, see <bpt id="p1">[</bpt>Configure the external vendor catalog<ept id="p1">](#configure-the-external-vendor-catalog)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby uzyskać szczegółowe informacje o tym zadaniu, zobacz temat <bpt id="p1">[</bpt>Konfigurowanie zewnętrznego katalogu dostawcy<ept id="p1">](#configure-the-external-vendor-catalog)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>Test the vendor’s external catalog configurations to verify that the settings are valid and that you can access the vendor’s external catalog.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przetestowanie konfiguracji zewnętrznego katalogu dostawcy w celu sprawdzenia, czy ustawienia są prawidłowe i czy masz dostęp do katalog.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>Use the <bpt id="p1">**</bpt>Validate settings<ept id="p1">**</ept> action to validate the request setup message that you’ve defined.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Za pomocą akcji <bpt id="p1">**</bpt>Sprawdź poprawność ustawień<ept id="p1">**</ept> zweryfikuj zdefiniowany przez siebie komunikat konfiguracji żądania.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>This message should cause the vendors external catalog site to be opened in a browser window.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ten komunikat powinien powodować otwieranie witryny zewnętrznego katalogu dostawcy w oknie przeglądarki internetowej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>During validation, you can’t order items and services from the vendor.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Podczas sprawdzania poprawności nie można zamawiać towarów ani usług od dostawcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>To order items and services, you must access the vendor’s catalog from a purchase requisition.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby zamawiać towary i usługi, należy przejść do katalogu dostawcy z poziomu zapotrzebowania na zakup.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Activate the external catalog by using the <bpt id="p1">**</bpt>Activate catalog<ept id="p1">**</ept> button on the <bpt id="p2">**</bpt>External catalogs<ept id="p2">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aktywacja zewnętrznego katalogu za pomocą przycisku <bpt id="p1">**</bpt>Uaktywnij katalog<ept id="p1">**</ept> znajdującego się na stronie <bpt id="p2">**</bpt>Katalogi zewnętrzne<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>The external catalog must be activated before employees can use it.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zewnętrzny katalog musi zostać aktywowany, zanim będą go mogli używać pracownicy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>You can inactivate the external catalog at any time.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zewnętrzny katalog można w dowolnym momencie zdezaktywować.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>Configure the external vendor catalog</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie zewnętrznego katalogu dostawcy</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>This section gives more details about task 4 in the preceding section.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tej sekcji dokładniej omówiono 4 zadania z poprzedniej części.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>Enter a name and description for the vendor’s external catalog.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wprowadź nazwę i opis katalogu zewnętrznego dostawcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>The name that you enter will appear on the cart that represents the external catalog that is shown to employees who creates a requisition.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wprowadzona nazwa pojawi się w koszyku reprezentującym zewnętrzny katalog, który będzie wyświetlany pracownikom tworzącym zapotrzebowania.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>Employees can click on the cart to open the catalog on the vendor’s external catalog site.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pracownicy mogą kliknąć koszyk, a zostanie otwarty katalog w witrynie zewnętrznego katalogu dostawcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Add an image by using the<bpt id="p1"> **</bpt>External catalog image<ept id="p1">**</ept> action.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dodaj obraz przy użyciu akcji <bpt id="p1"> **</bpt>Obraz z katalogu zewnętrznego<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>The image will appear on the cart that represents the external catalog that is shown to employees who create a requisition.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Obraz pojawi się w koszyku reprezentującym zewnętrzny katalog, który będzie wyświetlany pracownikom tworzącym zapotrzebowania.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>Note that the image’s width and height must be equal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Należy zwrócić uwagę, że szerokość i wysokość obrazu muszą być takie same.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Otherwise the image won’t be displayed correctly.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W przeciwnym razie obraz nie będzie wyświetlany poprawnie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>Select whether the vendor’s external catalog website should appear in the same browser window as the one where the employee has created the requisition, or if it should open in a new window.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Określ, czy witryna sieci Web zewnętrznego katalogu dostawcy ma być wyświetlana w tym samym oknie przeglądarki, w którym pracownik utworzył zapotrzebowanie, czy też w nowym oknie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>Select the vendor for the catalog.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz dostawcę dla katalogu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>In the <bpt id="p1">**</bpt>Legal entities<ept id="p1">**</ept> list, there is a row for each legal entity where the vendor is set up.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na liście <bpt id="p1">**</bpt>Firmy<ept id="p1">**</ept> jest wiersz dla każdej firmy, w której skonfigurowano dostawcę.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>To allow users to request products directly from the vendor’s catalog in some legal entities but not others, you can use the <bpt id="p1">**</bpt>Prevent access<ept id="p1">**</ept> or <bpt id="p2">**</bpt>Allow access<ept id="p2">**</ept> button for each legal entity where you want the catalog to be or not to be available.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby zezwolić użytkownikom na wnioskowanie o produkty bezpośrednio z katalogu dostawcy w niektórych firmach, a w innych nie, można użyć przycisku <bpt id="p1">**</bpt>Zabroń dostępu<ept id="p1">**</ept> lub <bpt id="p2">**</bpt>Zezwalaj na dostęp<ept id="p2">**</ept> dla każdej firmy, w której katalog ma być dostępny lub nie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>In the <bpt id="p1">**</bpt>Default expiration (Days)<ept id="p1">**</ept> field, enter the number of days that a quotation received from the external catalog is valid and can be used to purchase from the external vendor.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W polu <bpt id="p1">**</bpt>Domyślne wygaśnięcie (dni)<ept id="p1">**</ept> wprowadź liczbę dni, przez jaką oferta otrzymana z zewnętrznego katalogu jest ważna i może być używana do kupowania od zewnętrznego dostawcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>When a quotation is created and retrieved from the vendor’s external catalog site, the quotation is valid as of the current system date and remains valid for the number of days that you enter in this field.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po utworzeniu oferty i pobraniu jej z witryny zewnętrznego katalogu dostawcy oferta jest ważna na dzień określony bieżącą datą systemową i pozostaje ważna przez liczbę dni wprowadzoną w tym polu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Click the <bpt id="p1">**</bpt>Add<ept id="p1">**</ept> button to start mapping the procurement categories to the external catalog.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kliknij przycisk <bpt id="p1">**</bpt>Dodaj<ept id="p1">**</ept>, aby rozpocząć mapowanie kategorii zaopatrzenia na zewnętrzny katalog.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source> Then, in the Category name list, select a category.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"> Następnie na liście Nazwa kategorii wybierz kategorię.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>The list of categories is a superset of procurement categories that the vendor has been mapped to in all the legal entities that are set up for the vendor.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lista kategorii jest podzbiorem kategorii zaopatrzenia, do których zamapowano dostawcę we wszystkich firmach skonfigurowanych dla tego dostawcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>Procurement policies are used to allow or restrict access to categories for the buying legal entity or receiving operating unit.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zasady zaopatrzenia są używane w celu zezwolenia na dostęp lub ograniczenia dostępu do kategorii dla kupującej firmy lub przyjmującej jednostki operacyjnej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source> Punchout to an external catalog requires that access be allowed to at least one of the procurement categories that is mapped to the catalog.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"> Możliwość wybierania z zewnętrznego katalogu wymaga zezwolenia na dostęp do co najmniej jednej kategorii zaopatrzenia zamapowanej do katalogu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>Set up the cXML setup request message that will be sent to the vendor.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skonfiguruj komunikat żądania konfiguracji cXML, który będzie wysyłany dostawcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>The automatically generated message format is the minimal template that is required in order to start a session.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Format automatycznie generowanego komunikatu jest minimalnym szablonem wymaganym do rozpoczęcia sesji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>Fill in values for the tags.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wprowadź wartości znaczników.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>At any time, you can reload the system-generated message template by clicking <bpt id="p1">**</bpt>Restore message format<ept id="p1">**</ept>.<ph id="ph1"> </ph></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W dowolnym momencie można ponownie załadować systemowy szablon komunikatu, klikając przycisk <bpt id="p1">**</bpt>Przywróć format komunikatu<ept id="p1">**</ept>.<ph id="ph1"> </ph></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Note that if you restore the message format, the current message will be replaced by the automatically generated message format, which has empty tags.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Należy zauważyć, że jeśli przywrócisz format komunikatu, bieżący komunikat zostanie zastąpiony przez automatycznie wygenerowany format komunikatu, który ma puste znaczniki.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>cXML setup message</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Komunikat konfiguracyjny cXML</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Below you can find a description of the tags that are included in the template:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Poniżej znajduje się opis znaczników zawartych w szablonie:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>Field</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pole</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>Description</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">opis</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>&lt; Header &gt;&lt; From &gt;&lt; Credential domain=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Header &gt;&lt; From &gt;&lt; Credential domain=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>The domain of the buyer’s company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Domena firmy nabywcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>&lt; Header &gt;&lt; From &gt;&lt; Credential&gt;&lt; Identity &gt;&lt; /Identity &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Header &gt;&lt; From &gt;&lt; Credential&gt;&lt; Identity &gt;&lt; /Identity &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>The identity of the buyer’s company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tożsamość firmy nabywcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>&lt; Header &gt;&lt; To &gt;&lt; Credential domain=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Header &gt;&lt; To &gt;&lt; Credential domain=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>The domain of the vendor’s company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Domena firmy dostawcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>&lt; Header &gt;&lt; To &gt;&lt; Credential&gt;&lt; Identity &gt;&lt; /Identity&gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Header &gt;&lt; To &gt;&lt; Credential&gt;&lt; Identity &gt;&lt; /Identity&gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>The identity of the vendor’s company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tożsamość firmy dostawcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>&lt; Header &gt;&lt; Sender &gt;&lt; Credential domain=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Header &gt;&lt; Sender &gt;&lt; Credential domain=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>The domain of the buyer’s company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Domena firmy nabywcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>&lt; Header &gt;&lt; Sender &gt;&lt; Credential &gt;&lt; Identity &gt;&lt; /Identity&gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Header &gt;&lt; Sender &gt;&lt; Credential &gt;&lt; Identity &gt;&lt; /Identity&gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>The identity of the buyer’s company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tożsamość firmy nabywcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>&lt; Header &gt;&lt; Sender &gt;&lt; Credential &gt;&lt; SharedSecret &gt;&lt; /SharedSecret &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Header &gt;&lt; Sender &gt;&lt; Credential &gt;&lt; SharedSecret &gt;&lt; /SharedSecret &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>The shared secret for the buyer’s company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wspólny klucz tajny firmy nabywcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>&lt; Request deploymentMode=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Request deploymentMode=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>The test or production deployment.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Środowisko testowe lub produkcyjne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>&lt; Request &gt;&lt; PunchOutSetupRequest &gt;&lt; SupplierSetup &gt;&lt; URL &gt;&lt; /URL&gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Request &gt;&lt; PunchOutSetupRequest &gt;&lt; SupplierSetup &gt;&lt; URL &gt;&lt; /URL&gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>The URL of the vendor’s punchout endpoint.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Adres URL punktu końcowego z zewnętrznym katalogiem dostawcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Extrinsic elements</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Elementy zewnętrzne</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>An extrinsic element is additional information, such as a user name that is based on a user that punches out. The extrinsic element is set when the punchout occurs and it can be sent in the request setup message.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Element zewnętrzny to dodatkowe informacje, takie jak nazwa użytkownika, które zależy od użytkownika dokonującego wyboru w zewnętrznym katalogu. Element zewnętrzny jest ustawiany podczas wybierania w zewnętrznym katalogu i może być wysyłany w komunikacie żądania konfiguracji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>Your vendor could have a requirement for receiving an extrinsic element in the setup request.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dostawca może ustanowić wymóg, aby w żądaniu konfiguracji był mu przesyłany element zewnętrzny.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>In that case, you should add the extrinsic element to the list of extrinsic elements in the <bpt id="p1">**</bpt>Message format<ept id="p1">**</ept> section of the <bpt id="p2">**</bpt>External catalog<ept id="p2">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W takim przypadku należy dodać element zewnętrzny do listy elementów zewnętrznych na stronie <bpt id="p2">**</bpt>Katalog zewnętrzny<ept id="p2">**</ept> w sekcji <bpt id="p1">**</bpt>Format komunikatu<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>Specify a name for the extrinsic element that the vendor can recognize and map it to a value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nadaj elementowi zewnętrznemu nazwę, którą dostawca może rozpoznać, i zamapuj ją na wartość.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>The options for values are: User name, User email, or Random value.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Dostępne opcje wartości: Nazwa użytkownika, Adres e-mail użytkownika lub Wartość losowa.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>For more information about the cXML protocol, see the <bpt id="p1">[</bpt>cXML.org website<ept id="p1">](http://cxml.org/)</ept>.</source><target logoport:matchpercent="71" state="translated" state-qualifier="fuzzy-match">Więcej informacji o protokole cXML można znaleźć w <bpt id="p1">[</bpt>witrynie internetowej cXML.org<ept id="p1">](http://cxml.org/)</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>Post back message</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Komunikat ogłaszania zwrotnego</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>The post back message is the message that is received from the vendor when the user checks out from the external site and returns to Finance and Operations.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Komunikat ogłaszania zwrotnego to komunikat otrzymywany od dostawcy, gdy użytkownik finalizuje transakcję w zewnętrznej witrynie i wraca do programu Finance and Operations.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Post back messages can’t be configured.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Komunikatów ogłaszania zwrotnego nie można konfigurować.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>The messages are based on the cXML protocol definition.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Komunikat bazuje na definicji protokołu cXML.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source> Here is the information that can be part of the post back message that is received on a requisition line:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"> Poniżej przedstawiono informacje, które mogą wchodzić w skład komunikatu ogłaszania zwrotnego otrzymywanego w wierszu zapotrzebowania:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>Message received from vendor</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Komunikat otrzymywany od dostawcy</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>Copied to requisition line in Finance and Operations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Informacja kopiowana do wiersza zapotrzebowania w programie Finance and Operations</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>&lt; ItemIn quantity=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemIn quantity=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>Quantity</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ilość</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>&lt; ItemIn&gt;&lt; ItemID &gt;&lt; SupplierPartID &gt;&lt; /SupplierPartID &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemIn&gt;&lt; ItemID &gt;&lt; SupplierPartID &gt;&lt; /SupplierPartID &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>External item ID</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Identyfikator zewnętrznego towaru</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>&lt; ItemDetail&gt;&lt; UnitPrice &gt;&lt; Money currency=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemDetail&gt;&lt; UnitPrice &gt;&lt; Money currency=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>Currency</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Waluta</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>&lt; ItemDetail &gt;&lt; UnitPrice &gt;&lt; Money &gt;&lt; /Money &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemDetail &gt;&lt; UnitPrice &gt;&lt; Money &gt;&lt; /Money &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>Unit price</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cena jednostkowa</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>&lt; ItemDetail &gt;&lt; Description ShortName=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemDetail &gt;&lt; Description ShortName=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>Product name</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nazwa produktu</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>&lt; ItemDetail &gt;&lt; Description &gt;&lt; /Description &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemDetail &gt;&lt; Description &gt;&lt; /Description &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>Included in item description; Product name if ShortName is not specified.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zawarty w opisie towaru; Nazwa produktu, jeśli atrybut ShortName nie jest określony.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>&lt; ItemDetail &gt;&lt; UnitOfMeasure &gt;&lt; /UnitOfMeasure &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemDetail &gt;&lt; UnitOfMeasure &gt;&lt; /UnitOfMeasure &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>Unit</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jednostka</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>&lt; ItemDetail &gt;&lt; Classification &gt;&lt; /Classification &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemDetail &gt;&lt; Classification &gt;&lt; /Classification &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>Included in item description</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zawarty w opisie towaru</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>&lt; ItemDetail &gt;&lt; Classification domain=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemDetail &gt;&lt; Classification domain=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Included in item description</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zawarty w opisie towaru</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>Delete an external catalog</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Usuwanie katalogu zewnętrznego</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>Delete an external catalog with the Delete action on the page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Katalog zewnętrzny można usunąć za pomocą operacji Usuń dostępnej na stronie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>If a product from the external vendor catalog has been requested, the external vendor catalog cannot be deleted.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli poproszono o produkt z zewnętrznego katalogu dostawcy, nie można usunąć tego katalogu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>Instead, the status of the external vendor catalog is set to inactive.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zamiast tego dla katalogu jest ustawiany stan nieaktywności.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>If you want to remove access to the external vendor’s catalog site, but not delete it, change the external catalog status to Inactive.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli chcesz usunąć dostęp do witryny z zewnętrznym katalogiem dostawcy, ale bez usuwania samego katalogu, zmień stan zewnętrznego katalogu na Nieaktywny.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>