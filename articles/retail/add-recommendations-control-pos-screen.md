<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="add-recommendations-control-pos-screen.md" target-language="pl-PL">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>add-recommendations-control-pos-screen.54c686.f17da3db6fbc19548544a0c6c090a0b6db093673.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>f17da3db6fbc19548544a0c6c090a0b6db093673</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>e2fb0846fcc6298050a0ec82c302e5eb5254e0b5</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/27/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\add-recommendations-control-pos-screen.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Add a recommendations control to the transaction screen on POS devices</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dodawanie kontrolki rekomendacji do ekranu transakcji na urządzeniach z aplikacją POS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 for Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym temacie opisano sposób dodawania formantu rekomendacji do ekranu transakcji na urządzeniu w punkcie sprzedaży (POS) przy użyciu projektanta układu ekranu w programie Microsoft Dynamics 365 for Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Add a recommendations control to the transaction screen on POS devices</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dodawanie kontrolki rekomendacji do ekranu transakcji na urządzeniach z aplikacją POS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>We are removing the current version of the product recommendation service as we redesign this feature with a better algorithm and newer retail-oriented capabilities.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Usuwamy obecną wersję usługi rekomendowania produktów, ponieważ w nowej wersji wprowadzamy lepszy algorytm i nowsze funkcje zorientowane na handel detaliczny.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>For more information see <bpt id="p1">[</bpt>Removed or deprecated features<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby uzyskać więcej informacji, zobacz <bpt id="p1">[</bpt>Usunięte i przestarzałe funkcje<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 for Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym temacie opisano sposób dodawania formantu rekomendacji do ekranu transakcji na urządzeniu w punkcie sprzedaży (POS) przy użyciu projektanta układu ekranu w programie Microsoft Dynamics 365 for Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>You can display product recommendations on your POS device when you use Microsoft Dynamics 365 for Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rekomendacje produktów mogą być wyświetlane na urządzeniu punktu sprzedaży podczas używania programu Microsoft Dynamics 365 for Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source><bpt id="p1">*</bpt>Recommendations<ept id="p1">*</ept> are items that your customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">*</bpt>Rekomendacje<ept id="p1">*</ept> to towary, którymi odbiorca może być zainteresowany w związku z wcześniej dokonywanymi zakupami, towary na liście życzeń odbiorcy oraz towary, które inni podobni odbiorcy kupowali w sklepach internetowych i tradycyjnych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby wyświetlać rekomendacje produktów, należy za pomocą projektanta układu ekranu dodać formant do ekranu transakcji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Open Layout designer</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Otwieranie projektanta układu</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Channel setup<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>POS setup<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>POS<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Screen layouts<ept id="p5">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz kolejno opcje <bpt id="p1">**</bpt>Handel detaliczny<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Ustawienia kanału<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Ustawienia punktu sprzedaży<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>Punkt sprzedaży<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Układy ekranu<ept id="p5">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>Use the Quick Filter to find the screen that you want to add the control to.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Za pomocą szybkiego filtru znajdź ekran, do którego chcesz dodać formant.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>For example, filter on the <bpt id="p1">**</bpt>Screen layout ID<ept id="p1">**</ept> field using a value of <bpt id="p2">**</bpt>F2CP16:9M<ept id="p2">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">Na przykład wyfiltruj według pola <bpt id="p1">**</bpt>Identyfikator układu ekranu<ept id="p1">**</ept>, używając wartości <bpt id="p2">**</bpt>F2CP16:9M<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>In the list, find and select the desired record.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Na liście znajdź i zaznacz odpowiedni rekord.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>For example, select <bpt id="p1">**</bpt>Name: F2CP16:9M Screen Layout ID: F2CP16:9M<ept id="p1">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">Na przykład zaznacz pozycję <bpt id="p1">**</bpt>Nazwa: F2CP16:9M Identyfikator układu ekranu: F2CP16:9M<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Click <bpt id="p1">**</bpt>Layout designer<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Kliknij opcję <bpt id="p1">**</bpt>Projektant układu<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Follow the prompts to launch the layout designer.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Postępuj zgodnie z instrukcjami, aby uruchomić projektanta układu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from <bpt id="p1">**</bpt>Screen layouts<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gdy zostanie wyświetlony monit o poświadczenia, wpisz te same poświadczenia, które były używane przy uruchamianiu konstruktora układu ze strony <bpt id="p1">**</bpt>Układy ekranu<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>When you log in, a page similar to the one below appears.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po zalogowaniu się zobaczysz stronę podobną do przedstawionej poniżej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>The layout will be different depending on the customizations that were made for your store.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Układ może się różnić w zależności od dostosowań wprowadzonych dla sklepu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Layout designer<ept id="p1">](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</ept></source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Projektant układu<ept id="p1">](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Choose a display option</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Wybierz opcję wyświetlaną</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>There are two configurations options available.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Dostępne są dwie opcje konfiguracji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz opcję, która sprawdza się najlepiej dla Twojego sklepu, a następnie postępuj zgodnie z pozostałymi instrukcjami, aby dokończyć konfigurowanie formantu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>The two options are:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Oto te opcje:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>Recommendations are always visible.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rekomendacje są zawsze widoczne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>A <bpt id="p1">**</bpt>Recommendations<ept id="p1">**</ept> tab appears in the grid on the right side of the screen.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W siatce po prawej stronie ekranu jest wyświetlana karta <bpt id="p1">**</bpt>Zalecenia<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>Make recommendations always visible</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rekomendacje zawsze widoczne</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Zmniejsz wysokość obszaru szczegółów wierszy transakcji, tak aby była taka sama, jak wysokość panelu odbiorcy po lewej stronie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Height of the transaction lines details area reduced<ept id="p1">](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</ept></source><target logoport:matchpercent="70" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Zmniejszona wysokość obszaru szczegółów wierszy transakcji<ept id="p1">](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Z menu po lewej stronie przeciągnij formant rekomendacji i upuść go między obszar szczegółów wierszy transakcji a siatkę przycisków na środku w dolnej części ekranu transakcji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Resize the control so it fits in that space.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Zmień rozmiar formantu, tak aby mieścił się w tej przestrzeni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Recommendations control added to the layout<ept id="p1">](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</ept></source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Formant rekomendacji dodany do układu<ept id="p1">](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>Click the <bpt id="p1">**</bpt>X<ept id="p1">**</ept> to save and exit Layout designer.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Kliknij przycisk <bpt id="p1">**</bpt>X<ept id="p1">**</ept>, aby zapisać zmiany i zamknąć projektanta układu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>In Dynamics 365 for Retail, go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Retail IT<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Distribution schedules<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">W programie Dynamics 365 for Retail wybierz kolejno opcje <bpt id="p1">**</bpt>Handel detaliczny<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Dane IT sieci sprzedaży<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Harmonogramy dystrybucji<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>In the list, select<bpt id="p1"> **</bpt>1090 Registers<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na liście zaznacz pozycję <bpt id="p1"> **</bpt>1090 Kasy<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>Click <bpt id="p1">**</bpt>Run now<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kliknij przycisk <bpt id="p1">**</bpt>Uruchom teraz<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>Add a Recommendations tab to the button grid on the right side of the screen</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dodawanie karty Zalecenia do siatki przycisków po prawej stronie ekranu</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Right-click in the empty space below the last tab on the button grid located on the right side of the page.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Kliknij prawym przyciskiem myszy puste miejsce pod ostatnią kartą w siatce przycisków umieszczoną z prawej strony ekranu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Click<bpt id="p1"> **</bpt>Customize<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Kliknij przycisk<bpt id="p1"> **</bpt>Dostosuj<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Customization - Tab control dialog box<ept id="p1">](./media/pic-5.png)](./media/pic-5.png)</ept></source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Dostosowywanie — okno dialogowe Formant karty<ept id="p1">](./media/pic-5.png)](./media/pic-5.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Click <bpt id="p1">**</bpt>New tab<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Kliknij opcję <bpt id="p1">**</bpt>Nowa karta<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>Find the new tab that you just added.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Znajdź nową kartę, który została właśnie dodana.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>You may need to scroll down.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Może być konieczne przewinięcie ekranu w dół.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>In the <bpt id="p1">**</bpt>Contents<ept id="p1">**</ept> drop-down, select <bpt id="p2">**</bpt>Recommended products<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Na liście rozwijanej <bpt id="p1">**</bpt>Zawartość<ept id="p1">**</ept> wybierz opcję <bpt id="p2">**</bpt>Rekomendowane produkty<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Selecting Recommended products in the Contents field<ept id="p1">](./media/pic-6.png)](./media/pic-6.png)</ept></source><target logoport:matchpercent="76" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Wybieranie Rekomendowanych produktów w polu Zawartość<ept id="p1">](./media/pic-6.png)](./media/pic-6.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>In the <bpt id="p1">**</bpt>Label<ept id="p1">**</ept> field, type a name for the recommendations tab. For example, type 'Recommended products'.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">W polu <bpt id="p1">**</bpt>Etykieta<ept id="p1">**</ept> wpisz nazwę karty rekomendacji. Na przykład wpisz „Zalecane produkty”.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>In the <bpt id="p1">**</bpt>Image<ept id="p1">**</ept> field, select the image to appear on the tab.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W polu <bpt id="p1">**</bpt>Obraz<ept id="p1">**</ept> zaznacz ilustrację, która ma być wyświetlana na karcie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Click<bpt id="p1"> **</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kliknij<bpt id="p1"> **</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>The new tab appears in the button grid.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nowa karta zostanie wyświetlone w siatce przycisków.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>Click the <bpt id="p1">**</bpt>X<ept id="p1">**</ept> to save and exit Layout designer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kliknij przycisk <bpt id="p1">**</bpt>X<ept id="p1">**</ept>, aby zapisać zmiany i zamknąć projektanta układu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>In Dynamics 365 for Retail, go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Retail IT<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Distribution schedules<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W programie Dynamics 365 for Retail wybierz kolejno opcje <bpt id="p1">**</bpt>Handel detaliczny<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Dane IT sieci sprzedaży<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Harmonogramy dystrybucji<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>In the list, select<bpt id="p1"> **</bpt>1090 Registers<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na liście zaznacz pozycję <bpt id="p1"> **</bpt>1090 Kasy<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>Click <bpt id="p1">**</bpt>Run now<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kliknij przycisk <bpt id="p1">**</bpt>Uruchom teraz<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>Additional resources</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dodatkowe zasoby</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source><bpt id="p1">[</bpt>Personalized product recommendations overview<ept id="p1">](personalized-product-recommendations.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Omówienie spersonalizowanych rekomendacji produktów<ept id="p1">](personalized-product-recommendations.md)</ept></target></trans-unit>
      </group>
    </body>
  </file>
</xliff>