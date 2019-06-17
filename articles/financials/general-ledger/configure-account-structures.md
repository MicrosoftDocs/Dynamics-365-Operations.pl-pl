<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="configure-account-structures.md" target-language="pl-PL">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-d915bc8" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>configure-account-structures.6e0715.5fbd4b34d09b4ba8e1d34234c8e32268bba18778.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>5fbd4b34d09b4ba8e1d34234c8e32268bba18778</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>aec1dcd44274e9b8d0770836598fde5533b7b569</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>06/03/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\financials\general-ledger\configure-account-structures.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Configure account structures</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skonfiguruj strukturę konta</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic provides information about account structures and financial dimensions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ten temat zawiera informacje dotyczące struktury kont i wymiarów finansowych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Configure account structures</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Skonfiguruj strukturę konta</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>Account structures use the main account and financial dimensions to create a set of rules that determine the order and values used when entering the account number.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Struktury kont wykorzystują konto główne i wymiary finansowe do tworzenie zestawu reguł, które określają kolejność i wartości używane podczas wprowadzania numeru konta.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>You can set up as many account structures as you need for your business.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Można stworzyć dowolną liczbę struktur kont potrzebnych w firmie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>The account structures are assigned to a company’s ledger setup, so they can be shared.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Struktury konta są przypisywane do ustawień księgi firmy, więc mogą być współużytkowane.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>When creating an account structure, the maximum number of segments is 11.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Podczas tworzenia struktury konta maksymalna liczba segmentów to 11.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>If you need more segments than this, thoroughly evaluate your setup and requirements, as it will impact the user experience.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli potrzebujesz jeszcze więcej segmentów, kompleksowo oceń swoją konfigurację i wymagania, ponieważ wpłynie to na środowisko obsługi użytkowników.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Consider if a segment could be derived in a reporting scenario using a hierarchy instead of during data entry, or by using a user-defined field.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Należy wziąć pod uwagę, czy można utworzyć segment pochodny w scenariuszu raportowania przy użyciu hierarchii, a nie podczas wprowadzania danych, lub za pomocą pola zdefiniowane przez użytkownika.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>For example, if you want to report on location, but you can figure location by department or cost center, you would not need location as a financial dimension.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na przykład jeśli chcesz raportować z lokalizacji, ale nie można ustalić działu lub centrum kosztów, w którym znajduje się lokalizacja, nie potrzebujesz lokalizacji jako wymiaru finansowego.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>If after evaluation you do determine more than 11 segments are needed, you can add additional segments using advanced rules.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli po ocenie stwierdzisz, że potrzeba więcej niż 11 segmentów, można dodać kolejne segmenty za pomocą reguł zaawansowanych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>Account structures require the main account.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Struktury kont wymagają konta głównego.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>The main account does not need to be the first segment in the structure, but it does identify what account structure is being used during the account number entry.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konto główne nie musi być pierwszym segmentem w strukturze, ale wskazuje, jaka struktura konta jest używana podczas wprowadzania numeru konta.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Because of this, a main account value can only exist in one structure assigned to the ledger so that they do not overlap.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W związku z tym wartości konta głównego może istnieć tylko w jednej strukturze przypisanej do księgi, tak aby wartości nie zachodziły na siebie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>After the account structure is identified, the allowed values list is filtered to guide the user through picking only valid dimension values, decreasing the possibility of an incorrect journal entry.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po zidentyfikowaniu struktury konta zostanie wyfiltrowana lista dozwolonych wartości, pozwalając użytkownikowi wybierać tylko prawidłowe wartości wymiarów i w ten sposób zmniejszając ryzyko dokonania błędnego wpisu w arkuszu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>If you plan to budget against a financial dimension, it will need to be part of an account structure.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli masz zamiar budżetować względem wymiaru finansowego, musi on być częścią struktury konta.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Budgeting does not currently utilize advanced rules.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Obecnie mechanizm budżetowania nie korzysta z reguł zaawansowanych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przykład</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>To illustrate a best practice for setting up an account structure, let's assume that a company wants to track their balance sheet accounts (100000..399999) at the account and business unit financial dimension level.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby zilustrować najlepszy sposób konfigurowania struktury konta, załóżmy, że firma chce śledzić konta bilansowe (100000..399999) na poziomie konta i wymiaru finansowego jednostki biznesowej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>For revenue and expense accounts (400000..999999), they track financial dimensions Business Unit, Department, and Cost center.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dla kont przychodów i wydatków (400000..999999) śledzi wymiary finansowe Jednostka biznesowa, Dział i Centrum kosztów.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>If they make a sale, they also like to track Customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli coś sprzeda, chce również śledzić odbiorcę.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Using this scenario, it would be recommended to have two account structures assigned to the company’s ledger - one for Balance sheet accounts, and one for Profit and Loss accounts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W czasie używania tego scenariusza, zalecane jest posiadanie dwóch struktur kont przypisanych do księgi firmy — jeden dla kont bilansowych, a drugi dla rachunków zysków i strat.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>To optimize the user experience and validation, Customer should be an advanced rule that is only used when a sales account is used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby zoptymalizować czynności użytkownika i sprawdzanie poprawności, Odbiorca powinien być regułą zaawansowaną, która jest używana tylko w przypadku użycia konta sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source><bpt id="p1">**</bpt>Balance sheet account structure<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Struktura konta bilansowego<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Main account</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konto główne</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>Business unit</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jednostka biznesowa</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>100000..399999</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">100000..399999</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>*;” “</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">*;” “</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source><bpt id="p1">**</bpt>Profit and loss account structure<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Struktura konta wynikowego<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>Main account</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konto główne</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Business unit</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jednostka biznesowa</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Department</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dział</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>Cost center</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Centrum kosztu</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>400000..999999</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">400000..999999</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>*;” “</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">*;” “</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>*;” “</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">*;” “</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>*;” “</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">*;” “</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>*;” “</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">*;” “</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source><bpt id="p1">**</bpt>Advanced rule for adding a Customer<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Zaawansowana reguła dodawania odbiorcy<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Criteria: Where Main account is between 400000 and 499999, then add customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kryteria: Gdy konto główne mieści się w zakresie id 400000 do 499999, należy dodać odbiorcę.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>It cannot be left blank.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nie może pozostać puste.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Customer</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Odbiorca</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>In this simplified example, all values and blank are allowed so * and “ “ are used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym uproszczonym przykładzie są dozwolone wszystkie wartości i puste pole, więc są używane symbole * i „ ”.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>Segments and allowed values</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Segmenty i dozwolone wartości</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>The <bpt id="p1">**</bpt>Segments<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Allowed values details<ept id="p2">**</ept> section provides a grid like experience for entering the rules that will be followed on validation during posting.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sekcje <bpt id="p1">**</bpt>Segmenty<ept id="p1">**</ept> i <bpt id="p2">**</bpt>Szczegóły dozwolonych wartości<ept id="p2">**</ept> zawierają siatkę umożliwiającą wprowadzanie reguł, które będą egzekwowane podczas sprawdzania poprawności w trakcie księgowania.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>You can type directly in the cells in the grid, import it from Excel, or use the <bpt id="p1">**</bpt>Allowed value details<ept id="p1">**</ept> section to guide you through it.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Można wprowadzać tekst bezpośrednio w komórkach siatki, zaimportować go z programu Excel lub użyć sekcji <bpt id="p1">**</bpt>Szczegóły wartości dozwolonych<ept id="p1">**</ept> w celu otrzymania wskazówek wypełniania.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>The <bpt id="p1">**</bpt>Allowed value details<ept id="p1">**</ept> section guides you through creating criteria using <bpt id="p2">**</bpt>Operators<ept id="p2">**</ept> such as begins with, is between, includes, and many others.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Opcje w sekcji <bpt id="p1">**</bpt>Szczegóły dozwolonych wartości<ept id="p1">**</ept> prowadzą użytkownika przez proces tworzenia kryteriów za pomocą elementów <bpt id="p2">**</bpt>Operatory<ept id="p2">**</ept>, takich jak „zaczyna się od”, „zawiera się między”, „zawiera” itd.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Allow values<ept id="p1">](./media/account.png)](./media/account.png)</ept></source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Dozwolone wartości<ept id="p1">](./media/account.png)](./media/account.png)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Allowed values will default onto a journal or accounting distribution entry page when there are no other possible values to select according to the account structure setup.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Dozwolone wartości będą domyślne na stronie wprowadzania arkusza lub zasad podziału księgowań, jeśli nie istnieją inne wartości, które można wybrać zgodnie z ustawieniami struktury konta.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Here's an example of the <bpt id="p1">**</bpt>Profit and loss account structure<ept id="p1">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Oto przykład <bpt id="p1">**</bpt>struktury konta wynikowego<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>Main account</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Konto główne</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>Business unit</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Jednostka biznesowa</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>Department</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Dział</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>Cost center</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">MPK</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>400000..999999</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">400000..999999</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>002</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">002</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>022</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">022</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>014</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">014</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>When entering a journal and selecting an account in the profit and loss range, selecting business unit '002' will cause values 022 and 014 to be the default on the account control.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Podczas wprowadzania arkusza i wybierania konta w zakresie wyników wybranie jednostki biznesowej „002” spowoduje, że wartości 022 i 014 będą domyślne w formancie konta.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>This behavior will also occur with the accounting distribution page.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Takie zachowanie będzie również występowało na stronie zasady podziału księgowań.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>More than 7 criteria needed</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Potrzebna więcej niż 7 kryteriów</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>If you have more than 7 criteria that are needed, you can continue adding them on the next line.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Jeśli potrzebujesz więcej niż 7 kryteriów, możesz je dodać w następnym wierszu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>You will notice when working in the <bpt id="p1">**</bpt>Allowed value details<ept id="p1">**</ept> section that the <bpt id="p2">**</bpt>+Add new<ept id="p2">**</ept> criteria is nt longer active after the seventh criteria is entered.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Podczas pracy w sekcji <bpt id="p1">**</bpt>Szczegóły wartości dozwolonych<ept id="p1">**</ept>, że po wprowadzeniu siódmego kryterium nie jest już aktywne pole dodawania kryteriów <bpt id="p2">**</bpt>+Dodaj nowe<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>This is due to many factors such as:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jest to spowodowane wieloma czynnikami takimi jak:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>Column width</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Szerokość kolumny</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>How the data is stored</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sposób przechowywania danych</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>Performance of the <bpt id="p1">**</bpt>Allowed value details<ept id="p1">**</ept> control</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Działanie formantu <bpt id="p1">**</bpt>Szczegóły dozwolonych wartości<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>Usability</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zdatność</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>To continue to add additional criteria, click <bpt id="p1">**</bpt>Duplicate in the Segment<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Allowed values section<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby kontynuować dodawanie dodatkowych kryteriów, kliknij przycisk <bpt id="p1">**</bpt>Duplikuj segment<ept id="p1">**</ept> i <bpt id="p2">**</bpt>Sekcja dozwolonych wartości<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>This will copy the criteria to a new line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Spowoduje to skopiowanie kryteriów do nowego wiersza.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>You can then type over or modify the <bpt id="p1">**</bpt>Allowed value details<ept id="p1">**</ept> section.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Można następnie nadpisać lub zmodyfikować sekcję <bpt id="p1">**</bpt>Szczegóły wartości dozwolonych<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>Best practices</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Najlepsze praktyki</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>When setting up your account structures there are some best practices you can follow.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Podczas konfigurowania struktur kont zaleca się przestrzeganie pewnych najlepszych praktyk.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>However, this is only guidance so a holistic discussion about your business, growth plan, and maintenance plan should be considered as part of that discussion.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jednak jest to tylko wskazówka, a całościowa dyskusja powinna uwzględniać kwestie sytuacji firmy, planu rozwoju i planu konserwacji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>Make main account first or as close to the front of the account structure as possible, so users get the best guided experience they can during account entry.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Utwórz konto główne najpierw lub umieść je jak najbliżej z przodu struktury konta, tak aby podczas dokonywania zapisów na koncie użytkownicy byli najlepiej kierowani przez kolejne etapy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>Reuse account structures as much as possible to reduce maintenance across your legal entities.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W jak największym stopniu wykorzystuj istniejące struktury kont, aby uprościć zarządzanie we wszystkich firmach.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>For variations across legal entities, consider using advanced rules so that account structures can be reused.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dla odmian istniejących w różnych firmach należy rozważyć używanie reguł zaawansowanych, tak aby wykorzystywać istniejące struktury konta.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>When defining allowed values, use ranges and wildcards as much as possible.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Podczas definiowania dozwolonych wartości, należy użyć jak najwięcej zakresów i symboli wieloznacznych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>This not only allows you to grow and change without maintenance, but the system also performs more ideally with this configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nie tylko umożliwia to wzrost i zmianę bez obsługi technicznej, ale system również działa lepiej w tej konfiguracji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Do not just put an asterisk for every segment in the account structure and then solely rely on the advanced rules.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nie ograniczaj się tylko do umieszczenia gwiazdki obok każdego segmentu w strukturze konta, a następnie nie polegaj wyłącznie na regułach zaawansowanych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>This can be difficult to manage and often leads to user error during maintenance that can make the system unable to post.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Może to być trudne do zarządzania i często prowadzi do błędów użytkownika podczas obsługi technicznej, co może powodować niemożność zaksięgowania przez system.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>Account structure activation</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aktywacja struktury konta</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>When you are satifisfied with your new setup or a change to an account structure, you must activate it.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli nowe ustawienie lub zmiana struktury konta została zakończona, należy je aktywować.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>If an account structure is assigned to a ledger, this activation can be a long running process, as all unposted transactions in the system must be synced to the new structure.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli struktura konta jest przypisana do księgi, ten proces aktywacji może potrwać bardzo długo, ponieważ wszystkie niezaksięgowane transakcje w systemie muszą zostać zsynchronizowane z nową strukturą.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>Posted transactions are not impacted with account structure changes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zmiany struktury konta nie mają wpływu na zaksięgowane transakcje.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>For more information, see <bpt id="p1">[</bpt>Plan your chart of accounts<ept id="p1">](plan-chart-of-accounts.md)</ept>, <bpt id="p2">[</bpt>Financial dimensions<ept id="p2">](financial-dimensions.md)</ept> and <bpt id="p3">[</bpt>Enter account and dimension combinations (segmented entry control)<ept id="p3">](enter-account-dimension-combinations-segmented-entry-control.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby uzyskać więcej informacji, zobacz <bpt id="p1">[</bpt>Planowanie planu kont<ept id="p1">](plan-chart-of-accounts.md)</ept>, <bpt id="p2">[</bpt>Wymiary finansowe<ept id="p2">](financial-dimensions.md)</ept> i <bpt id="p3">[</bpt>Wpisywanie kombinacji wymiarów i kont (formant Wpis podzielony na segmenty)<ept id="p3">](enter-account-dimension-combinations-segmented-entry-control.md)</ept>.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>