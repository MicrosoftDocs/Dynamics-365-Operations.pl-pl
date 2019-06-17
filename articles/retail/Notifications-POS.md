<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="Notifications-POS.md" target-language="pl-PL">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>Notifications-POS.74d2b9.6c813cfea9b570e8dfd5dbe7f3ca1f4ba8594420.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>6c813cfea9b570e8dfd5dbe7f3ca1f4ba8594420</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>ffc37f7c2a63bada3055f37856a30424040bc9a3</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/16/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\Notifications-POS.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Show order notifications in the point of sale (POS)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pokazywanie powiadomień o zamówieniach w aplikacji POS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes how to enable order notifications in the point of sale and the notification framework.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym temacie opisano, w jaki sposób włączyć powiadomienia o zamówieniach w aplikacji POS i strukturze powiadomień.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Show order notifications in the point of sale (POS)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pokazywanie powiadomień o zamówieniach w aplikacji POS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>In the modern retail environment, store associates are assigned various tasks, such as helping customers, entering transactions, doing stock counts, and receiving orders in the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">We współczesnym środowisku sprzedaży detalicznej do pracowników sklepu są przypisane różne zadania, takie jak pomoc klientom, wprowadzanie transakcji, przeprowadzanie inwentaryzacji i odbieranie zamówień w sklepie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>The point of sale (POS) client provides a single application where associates can perform all these tasks and many others.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Klient punktu sprzedaży (POS) do jedna zintegrowana aplikacja, w której pracownicy mogą wykonywać te i wiele innych zadań.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>Because various tasks must be performed during the day, associates might have to be notified when something requires their attention.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ponieważ w ciągu dnia trzeba wykonywać różne zadania, pracownicy mogą potrzebować powiadomień, jeżeli coś wymaga ich uwagi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>The notification framework in the POS helps by letting retailers configure role-based notifications.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Struktura powiadomień w aplikacji POS rozwiązuje ten problem, umożliwiając pracownikom skonfigurowanie powiadomień opartych na rolach.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>In Microsoft Dynamics 365 for Retail with application update 5, these notifications can be configured only for POS operations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W Microsoft Dynamics 365 for Retail z aktualizacją aplikacji 5 te powiadomienia mogą być skonfigurowane tylko w dla operacji POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Currently, the system can show notifications only for order fulfillment operations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Obecnie system może być pokazywać powiadomienia tylko dla operacji realizacji zamówień.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>However, because the framework is designed to be extensible, developers will eventually be able to write a notification handler for any operation and show the notifications for that operation in the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jednak ponieważ struktura została zaprojektowana jako rozszerzalna, programiści docelowo będą mogli napisać programy obsługi powiadomień dla każdej operacji oraz powodować wyświetlanie tych powiadomień w aplikacji POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Enable notifications for order fulfillment operations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Włączanie powiadomień dla operacji realizacji zamówień</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>To enable notifications for order fulfillment operations, follow these steps.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby włączyć powiadomienia dla operacji realizacji zamówień, wykonaj poniższe czynności.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Channel setup<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>POS setup<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>POS<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Operations<ept id="p5">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz kolejno opcje <bpt id="p1">**</bpt>Handel detaliczny<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Ustawienia kanału<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Ustawienia punktu sprzedaży<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>Punkt sprzedaży<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Operacje<ept id="p5">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Search for the <bpt id="p1">**</bpt>Order fulfillment<ept id="p1">**</ept> operation, and select the <bpt id="p2">**</bpt>Enable notifications<ept id="p2">**</ept> check box for it to specify that the notification framework should listen to the handler for this operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wyszukaj operację <bpt id="p1">**</bpt>Realizacja zamówienia<ept id="p1">**</ept>, a następnie zaznacz pole wyboru <bpt id="p2">**</bpt>Włącz powiadomienia<ept id="p2">**</ept>, aby określić, że struktura powiadomień ma nasłuchiwać zdarzeń programu obsługi tej operacji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>If the handler is implemented, notifications for this operation will then be shown in the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli program obsługi jest zaimplementowany, powiadomienia o tej operacji będą wyświetlane w aplikacji POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Employees<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Workers<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph>, under Retail tab, open the POS permissions associated with the worker.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz kolejno opcje <bpt id="p1">**</bpt>Handel detaliczny<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Pracownicy etatowi<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Pracownicy<ept id="p3">**</ept><ph id="ph3">&amp;gt;</ph> i na karcie Handel detaliczny otwórz uprawnienia wobec aplikacji POS związane z pracownikiem.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Expand the <bpt id="p1">**</bpt>Notifications<ept id="p1">**</ept> FastTab, add the <bpt id="p2">**</bpt>Order fulfillment<ept id="p2">**</ept> operation, and set the <bpt id="p3">**</bpt>Display order<ept id="p3">**</ept> field to <bpt id="p4">**</bpt>1<ept id="p4">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rozwiń skróconą kartę <bpt id="p1">**</bpt>Powiadomienia<ept id="p1">**</ept>, dodaj operację <bpt id="p2">**</bpt>Realizacja zamówienia<ept id="p2">**</ept>, a następnie w polu <bpt id="p3">**</bpt>Kolejność wyświetlania<ept id="p3">**</ept> ustaw wartość <bpt id="p4">**</bpt>1<ept id="p4">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>If more than one notification is configured, this field is used to arrange the notifications.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeżeli skonfigurowano więcej niż jedno powiadomienie, to pole służy do określenia ich kolejności.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Notifications that have a lower <bpt id="p1">**</bpt>Display order<ept id="p1">**</ept> value appear above notifications that have a higher value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Powiadomienia o niższej wartości w polu <bpt id="p1">**</bpt>Kolejność wyświetlania<ept id="p1">**</ept> są wyświetlane nad powiadomieniami mającymi wyższą wartość.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>Notifications that have a <bpt id="p1">**</bpt>Display order<ept id="p1">**</ept> value of <bpt id="p2">**</bpt>1<ept id="p2">**</ept> are at the top.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Powiadomienia, które w polu <bpt id="p1">**</bpt>Kolejność wyświetlania<ept id="p1">**</ept> mają wartość <bpt id="p2">**</bpt>1<ept id="p2">**</ept>, znajdują się na samej górze.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Notifications are shown only for operations that are added on the <bpt id="p1">**</bpt>Notifications<ept id="p1">**</ept> FastTab, and you can add operations there only if the <bpt id="p2">**</bpt>Enable notifications<ept id="p2">**</ept> check box for those operations has been selected on the <bpt id="p3">**</bpt>POS operations<ept id="p3">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Powiadomienia są wyświetlane tylko dla operacji dodanych na skróconej karcie <bpt id="p1">**</bpt>Powiadomienia<ept id="p1">**</ept>, a operacje można tam dodawać tylko wtedy, gdy zaznaczono dla nich pole wyboru <bpt id="p2">**</bpt>Włącz powiadomienia<ept id="p2">**</ept> na stronie <bpt id="p3">**</bpt>Operacje aplikacji POS<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Additionally, notifications for an operation are shown to workers only if the operation is added to the POS permissions for those workers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ponadto powiadomienia o operacji są wyświetlane pracownikom tylko wtedy, gdy operacja została dodana do uprawnień wobec aplikacji POD dla tych pracowników.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Notifications can be overridden at the user level.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Powiadomienia można zastępować na poziomie użytkownika.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Open the worker's record, select <bpt id="p1">**</bpt>POS permissions<ept id="p1">**</ept>, and then edit the user's notification subscription.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Otwórz rekord pracownika, wybierz opcję <bpt id="p1">**</bpt>Uprawnienia punktu sprzedaży<ept id="p1">**</ept>, a następnie zmodyfikuj subskrypcję powiadomień dla użytkownika.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Channel setup<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>POS setup<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>POS profiles<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Functionality profiles<ept id="p5">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz kolejno opcje <bpt id="p1">**</bpt>Handel detaliczny<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Ustawienia kanału<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Ustawienia punktu sprzedaży<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>Profile punktów sprzedaży<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Profile funkcji<ept id="p5">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>In the <bpt id="p1">**</bpt>Notification interval<ept id="p1">**</ept> field, specify how often notifications should be pulled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W polu <bpt id="p1">**</bpt>Interwał powiadomień<ept id="p1">**</ept> określ żądaną częstotliwość pobierania powiadomień.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>For some notifications, the POS must make real-time calls to the back-office application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W przypadku niektórych powiadomień aplikacja POS musi wykonywać wywołania w czasie rzeczywistym do aplikacji zaplecza.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>These calls consume the compute capacity of your back-office application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Te wywołania zużywają moc obliczeniową aplikacji zaplecza.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Therefore, when you set the notification interval, you should consider both your business requirements and the impact of real-time calls to the back-office application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W związku z tym podczas ustawiania interwału między powiadomieniami należy wziąć pod uwagę zarówno swoje potrzeby biznesowe, jak i wpływ obsługi wywołań w czasie rzeczywistym na aplikację zaplecza.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>A value of <bpt id="p1">**</bpt>0<ept id="p1">**</ept> (zero) turns off notifications.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wartość <bpt id="p1">**</bpt>0<ept id="p1">**</ept> (zero) powoduje wyłączenie powiadomień.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Retail IT<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Distribution schedule<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz kolejno opcje <bpt id="p1">**</bpt>Handel detaliczny<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Dane IT sieci sprzedaży<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Harmonogram dystrybucji<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Select the <bpt id="p1">**</bpt>1060<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Staff<ept id="p2">**</ept>) schedule to synchronize notification subscription settings, and then select <bpt id="p3">**</bpt>Run now<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz harmonogram <bpt id="p1">**</bpt>1060<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Personel<ept id="p2">**</ept>), aby zsynchronizować ustawienia subskrypcji powiadomień, a następnie kliknij przycisk <bpt id="p3">**</bpt>Uruchom teraz<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>Next, select the <bpt id="p1">**</bpt>1070<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Channel configuration<ept id="p2">**</ept>) schedule to synchronize the permission interval, and then select <bpt id="p3">**</bpt>Run now<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Następnie wybierz harmonogram <bpt id="p1">**</bpt>1070<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Konfiguracja kanału<ept id="p2">**</ept>), aby zsynchronizować interwał uprawnień, i kliknij przycisk <bpt id="p3">**</bpt>Uruchom teraz<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>View notifications in the POS</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wyświetlanie powiadomień w aplikacji POS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>After you complete the preceding steps, the workers will be able to view the notifications in the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po wykonaniu powyższych kroków pracownicy będą widzieć powiadomienia w aplikacji POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>To view notifications, press the notification icon in the top right corner of the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby wyświetlić powiadomienia, naciśnij ikonę powiadomień w prawym górnym rogu aplikacji POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>A notification center appears and shows notifications for the order fulfillment operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zostanie wyświetlone centrum powiadomień z powiadomieniami o operacji realizacji zamówień.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>The notification center should show the following groups in the order fulfillment operation:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Centrum powiadomień powinno przedstawiać następujące grupy w operacji realizacji zamówień:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source><bpt id="p1">**</bpt>Store pickup<ept id="p1">**</ept> – This group shows the count of orders that have a delivery mode of <bpt id="p2">**</bpt>Pickup<ept id="p2">**</ept>, and that are scheduled for pickup from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Odbiór w sklepie<ept id="p1">**</ept> — ta grupa pokazuje liczbę zamówień, których sposób dostawy to <bpt id="p2">**</bpt>Odbiór<ept id="p2">**</ept>, a odbiór jest zaplanowany z bieżącego sklepu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>You can press the number on the group to open the <bpt id="p1">**</bpt>Order fulfillment<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Naciśnięcie liczby na grupie spowoduje otwarcie strony <bpt id="p1">**</bpt>Realizacja zamówienia<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>In this case, the page will be filtered so that it shows only the active orders that are set up for pickup from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym przypadku strona będzie wyfiltrowana, tak aby pokazywała tylko aktywne zamówienia skonfigurowane do odbioru z bieżącego sklepu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source><bpt id="p1">**</bpt>Ship from store<ept id="p1">**</ept> – This group shows the count of orders that have the delivery mode of <bpt id="p2">**</bpt>Shipping<ept id="p2">**</ept>, and that are scheduled for shipment from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Wyślij z magazynu<ept id="p1">**</ept> — ta grupa pokazuje liczbę zamówień, których sposób dostawy to <bpt id="p2">**</bpt>Wysyłka<ept id="p2">**</ept>, a wysyłka jest zaplanowana z bieżącego sklepu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>You can press the number on the group to open the <bpt id="p1">**</bpt>Order fulfillment<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Naciśnięcie liczby na grupie spowoduje otwarcie strony <bpt id="p1">**</bpt>Realizacja zamówienia<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>In this case, the page will be filtered so that it shows only the active orders that are set up for shipment from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym przypadku strona będzie wyfiltrowana, tak aby pokazywała tylko aktywne zamówienia skonfigurowane do wysyłki z bieżącego sklepu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>When new orders are assigned to the store for fulfillment, the notification icon changes to indicate that there are new notifications, and the count for the appropriate groups is updated.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gdy do sklepu zostaną przypisane nowe zamówienia do realizacji, ikona powiadomień zmieni się, informując o nowych powiadomieniach, a liczby odpowiednich grup zostaną zaktualizowane.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>Even though the groups are refreshed at regular intervals however, POS users can manually refresh the groups at any time by selecting the <bpt id="p1">**</bpt>Refresh<ept id="p1">**</ept> button next to the group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Grupy są odświeżane w regularnych odstępach czasu, ale użytkownicy aplikacji POS mogą również odświeżać je ręcznie w dowolnym momencie, naciskając przycisk <bpt id="p1">**</bpt>Odśwież<ept id="p1">**</ept> znajdujący się obok grupy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>Lastly, if a group has a new item, that the current worker hasn't viewed, then the group shows a burst symbol to indicate new content.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ponadto jeśli w grupie znajdzie się nowa pozycja, której pracownik jeszcze nie oglądał, obok grupy pojawi się symbol serii.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>Enable live content on POS buttons</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Włączanie przekazywania zawartości na żywo na przyciskach aplikacji POS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>POS buttons can now show a count to help workers easily determine which tasks require their immediate attention.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przyciski aplikacji POS mogą teraz pokazywać liczbę, aby ułatwić pracownikom identyfikowanie, które zadania wymagają ich natychmiastowej uwagi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>To show this number on a POS button, you must complete the notification setup that is described earlier in this topic (that is, you must enable notifications for an operation, set up a notification interval, and update the POS permission group for the worker).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby ta liczba była wyświetlana na przycisku aplikacji POS, należy dokonać konfiguracji powiadomień opisanej we wcześniejszej części tego tematu (tzn. trzeba włączyć powiadomienia dla operacji, ustawić interwał powiadamiania oraz zaktualizować grupę uprawnień pracownika wobec aplikacji POS).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>Additionally, you must open the button grid designer, view the button's properties, and select the <bpt id="p1">**</bpt>Enable live content<ept id="p1">**</ept> check box.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ponadto należy otworzyć projektanta siatki przycisków, wyświetlić właściwości przycisku i zaznaczyć pole wyboru <bpt id="p1">**</bpt>Włącz zawartości na żywo<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>In the <bpt id="p1">**</bpt>Content alignment<ept id="p1">**</ept> field, you can select whether the count appears in the upper-right corner of the button (<bpt id="p2">**</bpt>Top right<ept id="p2">**</ept>) or in the center (<bpt id="p3">**</bpt>Center<ept id="p3">**</ept>).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W polu <bpt id="p1">**</bpt>Wyrównanie zawartości<ept id="p1">**</ept> można określić, gdzie liczba ma być wyświetlana: w prawym górnym rogu (<bpt id="p2">**</bpt>Do góry, do prawej<ept id="p2">**</ept>) czy na środku (<bpt id="p3">**</bpt>Środek<ept id="p3">**</ept>) przycisku.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>The live content can be enabled for operations only if the <bpt id="p1">**</bpt>Enable notifications<ept id="p1">**</ept> check box has been selected for them on the <bpt id="p2">**</bpt>POS operations<ept id="p2">**</ept> page, as described earlier in this topic.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zawartości na żywo można włączyć dla operacji tylko wtedy, gdy na stronie <bpt id="p2">**</bpt>Operacje aplikacji POS<ept id="p2">**</ept> zaznaczono dla nich pole wyboru <bpt id="p1">**</bpt>Włącz powiadomienia<ept id="p1">**</ept>, jak opisano we wcześniejszej części tego tematu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>The following illustration shows the live content settings in the button grid designer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Poniższa ilustracja przedstawia ustawienia przekazywania zawartości na żywo w konstruktorze siatki przycisków.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source><bpt id="p1">![</bpt>Live content settings in the button grid designer<ept id="p1">]</ept><bpt id="p2">(./media/ButtonGridDesigner.png "</bpt>Live content settings in the button grid designer<ept id="p2">")</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">![</bpt>Ustawienia zawartości na żywo w konstruktorze siatki przycisków<ept id="p1">]</ept><bpt id="p2">(./media/ButtonGridDesigner.png "</bpt>Ustawienia zawartości na żywo w konstruktorze siatki przycisków<ept id="p2">")</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>To show the notification count on a button, you need to ensure that the correct screen layout is being updated.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby wyświetlić na przycisku licznik powiadomień, należy upewnić się, że jest aktualizowany właściwy układ ekranu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>To determine the screen layout that is being used by the POS, select the <bpt id="p1">**</bpt>Settings<ept id="p1">**</ept> icon in upper-right corner and note the <bpt id="p2">**</bpt>Screen layout ID<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Layout resolution<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby określić układ ekranu używany przez punkt sprzedaży, wybierz ikonę <bpt id="p1">**</bpt>Ustawienia<ept id="p1">**</ept> w prawym górnym rogu i zanotuj jej <bpt id="p2">**</bpt>Identyfikator układu ekranu<ept id="p2">**</ept> i <bpt id="p3">**</bpt>Rozdzielczość układu<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Now using Edge browser, go to the <bpt id="p1">**</bpt>Screen layout<ept id="p1">**</ept> page in Dynamics 365 for Finance and Operations, find the <bpt id="p2">**</bpt>Screen layout ID<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Layout resolution<ept id="p3">**</ept> identified above and select the <bpt id="p4">**</bpt>Enable live content<ept id="p4">**</ept> check box.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Za pomocą przeglądarki krawędzi przejdź do strony <bpt id="p1">**</bpt>Układ ekranu<ept id="p1">**</ept> w Dynamics 365 for Finance and Operations, znajdź <bpt id="p2">**</bpt>Identyfikator układu ekranu<ept id="p2">**</ept> i <bpt id="p3">**</bpt>Rozdzielczość układu<ept id="p3">**</ept> określone powyżej i zaznacz pole wyboru <bpt id="p4">**</bpt>Włącz zawartość na żywo<ept id="p4">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Go to <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Retail IT <ph id="ph2">\&gt;</ph> Distribution schedule<ept id="p1">**</ept> and run the 1090 (Registers) job to synchronize layout changes.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">Przejdź do <bpt id="p1">**</bpt>Sprzedaż detaliczna <ph id="ph1">\&gt;</ph> IT sprzedaży detalicznej <ph id="ph2">\&gt;</ph> Harmonogram dystrybucji<ept id="p1">**</ept> i uruchom zadanie 1090 (rejestry), aby zsynchronizować zmiany w układzie.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source><bpt id="p1">![</bpt>Find the screen layout used by POS<ept id="p1">]</ept><bpt id="p2">(./media/Choose_screen_layout.png "</bpt>Find the screen layout <ept id="p2">")</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">![</bpt>Znajdowanie układu ekranu używanego w punkcie sprzedaży<ept id="p1">]</ept><bpt id="p2">(./media/Choose_screen_layout.png "</bpt>Znajdź układ ekranu <ept id="p2">")</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>The following illustration shows the effect of selecting <bpt id="p1">**</bpt>Top right<ept id="p1">**</ept> versus <bpt id="p2">**</bpt>Center<ept id="p2">**</ept> in the <bpt id="p3">**</bpt>Content alignment<ept id="p3">**</ept> field for buttons of various sizes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na poniższej ilustracji przedstawiono efekt wybrania opcji <bpt id="p1">**</bpt>Do góry, do prawej<ept id="p1">**</ept> i <bpt id="p2">**</bpt>Środek<ept id="p2">**</ept> w polu <bpt id="p3">**</bpt>Wyrównanie zawartości<ept id="p3">**</ept> dla przycisków o różnej wielkości.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source><bpt id="p1">![</bpt>Live content on POS buttons<ept id="p1">]</ept><bpt id="p2">(./media/ButtonsWithLiveContent.png "</bpt>Live content on POS buttons<ept id="p2">")</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">![</bpt>Zawartość na żywo na przyciskach aplikacji POS<ept id="p1">]</ept><bpt id="p2">(./media/ButtonsWithLiveContent.png "</bpt>Zawartość na żywo na przyciskach aplikacji POS<ept id="p2">")</ept></target></trans-unit>
      </group>
    </body>
  </file>
</xliff>