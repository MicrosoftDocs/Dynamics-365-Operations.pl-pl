<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="cost.md" target-language="pl-PL">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>cost.4e88df.80e7a033467c3d94d55f06daa05f99bd27e19a29.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>80e7a033467c3d94d55f06daa05f99bd27e19a29</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>e2fb0846fcc6298050a0ec82c302e5eb5254e0b5</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/27/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\cost.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Cost configuration for distributed order management (DOM)</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Konfiguracja kosztów dla funkcji zarządzania zamówieniami rozdzielonymi (DOM)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes cost configuration for the distributed order management (DOM) functionality in Microsoft Dynamics 365 for Retail.</source><target logoport:matchpercent="77" state="translated" state-qualifier="fuzzy-match">W tym temacie opisano konfigurację kosztów dla funkcji zarządzania zamówieniami rozdzielonymi (DOM) w rozwiązaniu Microsoft Dynamics 365 for Retail.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Cost configuration for distributed order management (DOM)</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Konfiguracja kosztów dla funkcji zarządzania zamówieniami rozdzielonymi (DOM)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>Organizations consider multiple cost components to determine the optimal location to fulfill an order from.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Organizacje używają wielu składników kosztów w celu ustalenia optymalnej lokalizacji, z której ma zostać zrealizowane zamówienie.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>Some of these cost components are shipping cost, handling cost, and packaging cost.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Niektóre z tych składników kosztów to koszty wysyłki, koszty obsługi i koszty pakowania.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>A combination of these costs is calculated to determine the fulfillment location.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Kombinacja tych kosztów jest obliczana w celu ustalenia lokalizacji realizacji.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>When the first iteration of distributed order management (DOM) in Microsoft Dynamics 365 for Retail optimized the assignment of orders to fulfillment locations, it factored in distance only.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Gdy w wyniku pierwszej iteracji zarządzania zamówieniami rozdzielonymi (DOM) w rozwiązaniu Microsoft Dynamics 365 for Retail byłą wykonywana optymalizacja przypisań zamówień do lokalizacji realizacji, była brana pod uwagę tylko odległość.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Although distance can be correlated with cost, it isn't the same as cost.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Mimo że odległość może być skorelowana z kosztami, nie jest tym samym, co koszt.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>For example, an overnight shipping method costs more than three-day shipping or seven-day shipping over the same distance.</source><target logoport:matchpercent="0" state="translated">Na przykład wysyłka w ciągu jednej nocy kosztuje więcej niż wysyłka w ciągu trzech lub siedmiu dni na tę samą odległość.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>The cost configuration feature lets retailers define and configure additional cost components that will be calculated and factored in to determine the optimal location to fulfill order lines from.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Funkcja konfiguracji kosztów umożliwia sprzedawcom detalicznym definiowanie i konfigurowanie dodatkowych składników kosztów, które będą obliczane i uwzględniane w celu ustalenia optymalnej lokalizacji, z której mają być realizowane wiersze zamówienia.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>When cost components are configured, the DOM solver uses only those cost definitions to determine the optimal location for order fulfillment.</source><target logoport:matchpercent="0" state="translated">W przypadku skonfigurowania składników kosztów moduł obliczeniowy DOM używa tylko tych definicji kosztów w celu ustalenia optymalnej lokalizacji realizacji zamówienia.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>It doesn't consider the distance component as a cost.</source><target logoport:matchpercent="0" state="translated">Ten moduł nie traktuje składnika odległości jako kosztu.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>However, if no cost components are configured, the DOM solver does use the distance component as a cost to determine the optimal location for order fulfillment.</source><target logoport:matchpercent="72" state="translated" state-qualifier="fuzzy-match">Jeśli jednak składniki kosztów nie zostaną skonfigurowane, moduł obliczeniowy DOM będzie używał składnika odległości jako kosztu w celu ustalenia optymalnej lokalizacji realizacji zamówienia.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Set up cost components</source><target logoport:matchpercent="0" state="translated">Konfigurowanie składników kosztów</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Two major cost component types can be defined in the system: <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Other<ept id="p2">**</ept>.</source><target logoport:matchpercent="0" state="translated">W systemie można zdefiniować dwa główne typy składników kosztów: <bpt id="p1">**</bpt>Wysyłka<ept id="p1">**</ept> i <bpt id="p2">**</bpt>Inne<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Both cost component types support multiple calculation bases, as shown in the following table.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Oba typy składników kosztów obsługują wiele podstaw obliczania, tak jak pokazano w poniższej tabeli.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Cost component type</source><target logoport:matchpercent="76" state="translated" state-qualifier="fuzzy-match">Typ składnika kosztów</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Calculation basis</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Podstawa obliczania</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Shipping</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Wysyłka</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>Simple</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">Proste</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Tiered</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Wielopoziomowe</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Other</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">Inne</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Sales order</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Zamówienie sprzedaży</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Sales line</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">Wiersz sprzedaży</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Location</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Lokalizacja</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>Shipping cost component type</source><target logoport:matchpercent="77" state="translated" state-qualifier="fuzzy-match">Typ składnika kosztów Wysyłka</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>This section explains how to set up each combination of the <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> cost component type and a calculation basis for shipping costs.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">W tej sekcji opisano sposób konfigurowania poszczególnych kombinacji typu składnika kosztów <bpt id="p1">**</bpt>Wysyłka<ept id="p1">**</ept> oraz podstawy obliczania kosztów wysyłki.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>It also explains how the DOM solver uses each combination.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Wyjaśniono również, w jaki sposób moduł obliczeniowy DOM używa każdej kombinacji.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Cost component type = Shipping and Calculation basis = Simple</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Typ składnika kosztów = Wysyłka; Podstawa obliczania = Proste</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>If a combination of the <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> cost component type and the <bpt id="p2">**</bpt>Simple<ept id="p2">**</ept> calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</source><target logoport:matchpercent="0" state="translated">Jeśli jest używana kombinacja typu składnika kosztów <bpt id="p1">**</bpt>Wysyłka<ept id="p1">**</ept> i podstawa obliczania <bpt id="p2">**</bpt>Proste<ept id="p2">**</ept>, koszt wysyłki dla metody dostawy jest oparty na ustalonym koszcie lub odległości.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>You must set up the following fields for this combination:</source><target logoport:matchpercent="0" state="translated">Dla tej kombinacji musisz skonfigurować następujące pola:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source><bpt id="p1">**</bpt>Cost factor<ept id="p1">**</ept> – Enter a unique identifier for the cost factor.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Współczynnik kosztu<ept id="p1">**</ept> — umożliwia wprowadzenie unikatowego identyfikatora współczynnika kosztu.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source><bpt id="p1">**</bpt>Description<ept id="p1">**</ept> – Enter the name and description of the cost factor.</source><target logoport:matchpercent="78" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Opis<ept id="p1">**</ept> — umożliwia wprowadzenie nazwy i opisu współczynnika kosztu.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source><bpt id="p1">**</bpt>Start date<ept id="p1">**</ept> and <bpt id="p2">**</bpt>End date<ept id="p2">**</ept> – You can use these fields to limit the cost factor for a specific date range.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Data rozpoczęcia<ept id="p1">**</ept> i <bpt id="p2">**</bpt>Data zakończenia<ept id="p2">**</ept> — za pomocą tych pól możesz ograniczyć współczynnik kosztu do określonego zakresu dat.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>If you leave these fields blank, the cost factor is valid for an indefinite period.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Jeśli zostawisz te pola puste, współczynnik kosztu będzie prawidłowy w nieskończonym okresie.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source><bpt id="p1">**</bpt>Active<ept id="p1">**</ept> – Indicate whether the cost factor is active.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Aktywny<ept id="p1">**</ept> — umożliwia wskazanie, czy dany współczynnik kosztu jest aktywny.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>The DOM considers only active cost factors that are associated with the fulfillment profile.</source><target logoport:matchpercent="0" state="translated">Funkcja zarządzania zamówieniami rozdzielonymi uwzględnia tylko aktywne współczynniki kosztów, które są skojarzone z profilem realizacji.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source><bpt id="p1">**</bpt>Company<ept id="p1">**</ept> – Specify the legal entity that the cost factor is configured for.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Firma<ept id="p1">**</ept> — umożliwia określenie firmy, dla której jest konfigurowany współczynnik kosztu.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>All lines of the calculation criteria must be for the same legal entity.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Wszystkie wiersze kryteriów obliczania muszą dotyczyć tej samej firmy.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source><bpt id="p1">**</bpt>Modes of delivery<ept id="p1">**</ept> – Specify the modes of delivery that the cost is configured for.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Metody dostawy<ept id="p1">**</ept> — umożliwia określenie metod dostawy, dla których jest konfigurowany koszt.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source><bpt id="p1">**</bpt>Calculation type<ept id="p1">**</ept> – Specify how the cost should be calculated for a specific mode of delivery.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Typ obliczania<ept id="p1">**</ept> — umożliwia określenie sposobu obliczania kosztu dla określonej metody dostawy.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Two calculation types are supported:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Obsługiwane są dwa typy obliczania:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source><bpt id="p1">**</bpt>Fixed<ept id="p1">**</ept> – A flat cost is used for the mode of delivery.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Stały<ept id="p1">**</ept> — dla metody dostawy jest używany ustalony koszt.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>If you select this calculation type, the <bpt id="p1">**</bpt>Cost<ept id="p1">**</ept> field defines the flat cost.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">W przypadku wybrania tego typu obliczania w polu <bpt id="p1">**</bpt>Koszt<ept id="p1">**</ept> należy zdefiniować ustalony koszt.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source><bpt id="p1">**</bpt>Per-distance unit<ept id="p1">**</ept> – The cost for the mode of delivery is calculated as the cost value that is specified in the <bpt id="p2">**</bpt>Cost<ept id="p2">**</ept> field times the distance between the delivery address and the locations.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Na jednostkę odległości<ept id="p1">**</ept> — koszt dla metody dostawy jest obliczany jako iloczyn wartość kosztu określonej w polu <bpt id="p2">**</bpt>Koszt<ept id="p2">**</ept> i odległości między adresem dostawy a lokalizacjami.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source><bpt id="p1">**</bpt>Cost<ept id="p1">**</ept> – Specify the cost value that is used in conjunction with the <bpt id="p2">**</bpt>Calculation type<ept id="p2">**</ept> field to compute the cost for a mode of delivery.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Koszt<ept id="p1">**</ept> — umożliwia określenie wartości kosztu używanej w połączeniu z polem <bpt id="p2">**</bpt>Typ obliczania<ept id="p2">**</ept> w celu obliczenia kosztu dla metody dostawy.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>Cost component type = Shipping and Calculation basis = Tiered</source><target logoport:matchpercent="87" state="translated" state-qualifier="fuzzy-match">Typ składnika kosztów = Wysyłka; Podstawa obliczania = Wielopoziomowe</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>If a combination of the <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> cost component type and the <bpt id="p2">**</bpt>Tiered<ept id="p2">**</ept> calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</source><target logoport:matchpercent="95" state="translated" state-qualifier="fuzzy-match">Jeśli jest używana kombinacja typu składnika kosztów <bpt id="p1">**</bpt>Wysyłka<ept id="p1">**</ept> i podstawa obliczania <bpt id="p2">**</bpt>Wielopoziomowe<ept id="p2">**</ept>, koszt wysyłki dla metody dostawy jest oparty na ustalonym koszcie lub odległości.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>However, in this combination, the distance is based on a tiered range of distances.</source><target logoport:matchpercent="0" state="translated">Jednak w przypadku tej kombinacji odległość jest oparta na wielopoziomowym zakresie odległości.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>You must set up the following fields for this combination:</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Dla tej kombinacji musisz skonfigurować następujące pola:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source><bpt id="p1">**</bpt>Cost factor<ept id="p1">**</ept> – Enter a unique identifier for the cost factor.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Współczynnik kosztu<ept id="p1">**</ept> — umożliwia wprowadzenie unikatowego identyfikatora współczynnika kosztu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source><bpt id="p1">**</bpt>Description<ept id="p1">**</ept> – Enter the name and description of the cost factor.</source>
        <target logoport:matchpercent="78" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Opis<ept id="p1">**</ept> — umożliwia wprowadzenie nazwy i opisu współczynnika kosztu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source><bpt id="p1">**</bpt>Default cost<ept id="p1">**</ept> – Specify the cost that should be used for a mode of delivery if the distance between the delivery address and the location doesn't fall into any of the tiered distances for the mode of delivery.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Koszt domyślny<ept id="p1">**</ept> — umożliwia określenie kosztu, który ma być używany dla metody dostawy, jeśli odległość między adresem dostawy a lokalizacją nie należy do żadnej wielopoziomowej odległości ustalonej dla metody dostawy.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source><bpt id="p1">**</bpt>Start date<ept id="p1">**</ept> and <bpt id="p2">**</bpt>End date<ept id="p2">**</ept> – You can use these fields to limit the cost factor for a specific date range.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Data rozpoczęcia<ept id="p1">**</ept> i <bpt id="p2">**</bpt>Data zakończenia<ept id="p2">**</ept> — za pomocą tych pól możesz ograniczyć współczynnik kosztu do określonego zakresu dat.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>If you leave these fields blank, the cost factor is valid for an indefinite period.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Jeśli zostawisz te pola puste, współczynnik kosztu będzie prawidłowy w nieskończonym okresie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source><bpt id="p1">**</bpt>Active<ept id="p1">**</ept> – Indicate whether the cost factor is active.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Aktywny<ept id="p1">**</ept> — umożliwia wskazanie, czy dany współczynnik kosztu jest aktywny.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>The DOM considers only active cost factors that are associated with the fulfillment profile.</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Funkcja zarządzania zamówieniami rozdzielonymi uwzględnia tylko aktywne współczynniki kosztów, które są skojarzone z profilem realizacji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source><bpt id="p1">**</bpt>Company<ept id="p1">**</ept> – Specify the legal entity that the cost factor is configured for.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Firma<ept id="p1">**</ept> — umożliwia określenie firmy, dla której jest konfigurowany współczynnik kosztu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>All lines of the calculation criteria must be for the same legal entity.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Wszystkie wiersze kryteriów obliczania muszą dotyczyć tej samej firmy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source><bpt id="p1">**</bpt>Modes of delivery<ept id="p1">**</ept> – Specify the modes of delivery that the cost is configured for.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Metody dostawy<ept id="p1">**</ept> — umożliwia określenie metod dostawy, dla których jest konfigurowany koszt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source><bpt id="p1">**</bpt>Distance type<ept id="p1">**</ept> – Specify whether the tiered distance definition is an aerial distance or a road distance.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Typ odległości<ept id="p1">**</ept> — umożliwia określenie, czy definicja odległości wielopoziomowej to odległość lotnicza, czy drogowa.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source><bpt id="p1">**</bpt>Distance units<ept id="p1">**</ept> – Specify the unit that the tiered distance is measured in.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Jednostki odległości<ept id="p1">**</ept> — umożliwia określenie jednostki, w której będzie mierzona odległość wielopoziomowa.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source><bpt id="p1">**</bpt>Distance from<ept id="p1">**</ept> – Specify the start range for the tiered distance.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Odległość od<ept id="p1">**</ept> — określa zakres początkowy dla odległości wielopoziomowej.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source><bpt id="p1">**</bpt>Distance to<ept id="p1">**</ept> – Specify the end range for the tiered distance.</source><target logoport:matchpercent="82" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Odległość do<ept id="p1">**</ept> — określa zakres końcowy dla odległości wielopoziomowej.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source><bpt id="p1">**</bpt>Calculation type<ept id="p1">**</ept> – Specify how the cost should be calculated for a specific mode of delivery and tiered distance.</source><target logoport:matchpercent="85" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Typ obliczania<ept id="p1">**</ept> — umożliwia określenie sposobu obliczania kosztu dla określonej metody dostawy i odległości wielopoziomowej.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Two calculation types are supported:</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Obsługiwane są dwa typy obliczania:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source><bpt id="p1">**</bpt>Fixed<ept id="p1">**</ept> – A flat cost is used for the mode of delivery.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Stały<ept id="p1">**</ept> — dla metody dostawy jest używany ustalony koszt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>If you select this calculation type, the <bpt id="p1">**</bpt>Cost<ept id="p1">**</ept> field defines the flat cost.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">W przypadku wybrania tego typu obliczania w polu <bpt id="p1">**</bpt>Koszt<ept id="p1">**</ept> należy zdefiniować ustalony koszt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source><bpt id="p1">**</bpt>Per distance unit<ept id="p1">**</ept> – The cost for the mode of delivery and tiered distance is calculated as the cost value that is specified in the <bpt id="p2">**</bpt>Cost<ept id="p2">**</ept> field times the distance between the delivery address and the locations.</source><target logoport:matchpercent="90" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Na jednostkę odległości<ept id="p1">**</ept> — koszt dla metody dostawy i odległości wielopoziomowej jest obliczany jako iloczyn wartość kosztu określonej w polu <bpt id="p2">**</bpt>Koszt<ept id="p2">**</ept> i odległości między adresem dostawy a lokalizacjami.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source><bpt id="p1">**</bpt>Cost<ept id="p1">**</ept> – Specify the cost value that is used in conjunction with the <bpt id="p2">**</bpt>Calculation type<ept id="p2">**</ept> field to compute the cost for a mode of delivery.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Koszt<ept id="p1">**</ept> — umożliwia określenie wartości kosztu używanej w połączeniu z polem <bpt id="p2">**</bpt>Typ obliczania<ept id="p2">**</ept> w celu obliczenia kosztu dla metody dostawy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>When you define tiered distances, the system validates that there are no missing or overlapping distances.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Podczas definiowania odległości wielopoziomowych system sprawdza, czy nie brakuje żadnych odległości i czy jakiekolwiek odległości nie nakładają się na siebie.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>The distance type that is used for a mode of delivery must be the same across all the tiered distances.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Typ odległości używany dla metody dostawy musi być taki sam dla wszystkich odległości wielopoziomowych.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Other cost component type</source><target logoport:matchpercent="77" state="translated" state-qualifier="fuzzy-match">Typ składnika kosztów Inny</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>This section explains how to set up each combination of the <bpt id="p1">**</bpt>Other<ept id="p1">**</ept> cost component type and an other cost type for non-shipping costs.</source><target logoport:matchpercent="80" state="translated" state-qualifier="fuzzy-match">W tej sekcji opisano sposób konfigurowania poszczególnych kombinacji typu składnika kosztów <bpt id="p1">**</bpt>Inny<ept id="p1">**</ept> oraz innego typu koszu dla kosztów niezwiązanych z wysyłką.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>It also explains how the DOM solver uses each combination.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Wyjaśniono również, w jaki sposób moduł obliczeniowy DOM używa każdej kombinacji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>Cost component type = Other and Other cost type = Sales order</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Typ składnika kosztów = Inny; Inny typ kosztu = Zamówienie sprzedaży</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>A combination of the <bpt id="p1">**</bpt>Other<ept id="p1">**</ept> cost component type and the <bpt id="p2">**</bpt>Sales order<ept id="p2">**</ept> other cost type is used to define non-shipping costs at the sales order level.</source><target logoport:matchpercent="0" state="translated">Kombinacja typu składnika kosztów <bpt id="p1">**</bpt>Inny<ept id="p1">**</ept> oraz innego typu kosztu <bpt id="p2">**</bpt>Zamówienie sprzedaży<ept id="p2">**</ept> służy do definiowania kosztów niezwiązanych z wysyłką na poziomie zamówienia sprzedaży.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>You must set up the following fields for this combination:</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Dla tej kombinacji musisz skonfigurować następujące pola:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source><bpt id="p1">**</bpt>Cost factor<ept id="p1">**</ept> – Enter a unique identifier for the cost factor.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Współczynnik kosztu<ept id="p1">**</ept> — umożliwia wprowadzenie unikatowego identyfikatora współczynnika kosztu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source><bpt id="p1">**</bpt>Description<ept id="p1">**</ept> – Enter the name and description of the cost factor.</source>
        <target logoport:matchpercent="78" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Opis<ept id="p1">**</ept> — umożliwia wprowadzenie nazwy i opisu współczynnika kosztu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source><bpt id="p1">**</bpt>Start date<ept id="p1">**</ept> and <bpt id="p2">**</bpt>End date<ept id="p2">**</ept> – You can use these fields to limit the cost factor for a specific date range.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Data rozpoczęcia<ept id="p1">**</ept> i <bpt id="p2">**</bpt>Data zakończenia<ept id="p2">**</ept> — za pomocą tych pól możesz ograniczyć współczynnik kosztu do określonego zakresu dat.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>If you leave these fields blank, the cost factor is valid for an indefinite period.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Jeśli zostawisz te pola puste, współczynnik kosztu będzie prawidłowy w nieskończonym okresie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source><bpt id="p1">**</bpt>Active<ept id="p1">**</ept> – Indicate whether the cost factor is active.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Aktywny<ept id="p1">**</ept> — umożliwia wskazanie, czy dany współczynnik kosztu jest aktywny.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>The DOM considers only active cost factors that are associated with the fulfillment profile.</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Funkcja zarządzania zamówieniami rozdzielonymi uwzględnia tylko aktywne współczynniki kosztów, które są skojarzone z profilem realizacji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source><bpt id="p1">**</bpt>Cost<ept id="p1">**</ept> – Specify the cost value for a non-shipping cost at the sales order level.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Koszt<ept id="p1">**</ept> — umożliwia określenie wartości kosztu niezwiązanego z wysyłką na poziomie zamówienia sprzedaży.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>Cost component type = Other and Other cost type = Sales line</source><target logoport:matchpercent="89" state="translated" state-qualifier="fuzzy-match">Typ składnika kosztów = Inny; Inny typ kosztu = Wiersz sprzedaży</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>A combination of the <bpt id="p1">**</bpt>Other<ept id="p1">**</ept> cost component type and the <bpt id="p2">**</bpt>Sales line<ept id="p2">**</ept> other cost type is used to define non-shipping costs at the sales order line level.</source><target logoport:matchpercent="93" state="translated" state-qualifier="fuzzy-match">Kombinacja typu składnika kosztów <bpt id="p1">**</bpt>Inny<ept id="p1">**</ept> oraz innego typu kosztu <bpt id="p2">**</bpt>Wiersz sprzedaży<ept id="p2">**</ept> służy do definiowania kosztów niezwiązanych z wysyłką na poziomie wiersza zamówienia sprzedaży.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>You must set up the following fields for this combination:</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Dla tej kombinacji musisz skonfigurować następujące pola:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source><bpt id="p1">**</bpt>Cost factor<ept id="p1">**</ept> – Enter a unique identifier for the cost factor.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Współczynnik kosztu<ept id="p1">**</ept> — umożliwia wprowadzenie unikatowego identyfikatora współczynnika kosztu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source><bpt id="p1">**</bpt>Description<ept id="p1">**</ept> – Enter the name and description of the cost factor.</source>
        <target logoport:matchpercent="78" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Opis<ept id="p1">**</ept> — umożliwia wprowadzenie nazwy i opisu współczynnika kosztu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source><bpt id="p1">**</bpt>Start date<ept id="p1">**</ept> and <bpt id="p2">**</bpt>End date<ept id="p2">**</ept> – You can use these fields to limit the cost factor for a specific date range.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Data rozpoczęcia<ept id="p1">**</ept> i <bpt id="p2">**</bpt>Data zakończenia<ept id="p2">**</ept> — za pomocą tych pól możesz ograniczyć współczynnik kosztu do określonego zakresu dat.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>If you leave these fields blank, the cost factor is valid for an indefinite period.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Jeśli zostawisz te pola puste, współczynnik kosztu będzie prawidłowy w nieskończonym okresie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source><bpt id="p1">**</bpt>Active<ept id="p1">**</ept> – Indicate whether the cost factor is active.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Aktywny<ept id="p1">**</ept> — umożliwia wskazanie, czy dany współczynnik kosztu jest aktywny.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>The DOM considers only active cost factors that are associated with the fulfillment profile.</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Funkcja zarządzania zamówieniami rozdzielonymi uwzględnia tylko aktywne współczynniki kosztów, które są skojarzone z profilem realizacji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source><bpt id="p1">**</bpt>Cost<ept id="p1">**</ept> – Specify the cost value for a non-shipping cost at the sales order line level.</source><target logoport:matchpercent="94" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Koszt<ept id="p1">**</ept> — umożliwia określenie wartości kosztu niezwiązanego z wysyłką na poziomie wiersza zamówienia sprzedaży.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>Cost component type = Other and Other cost type = Location</source><target logoport:matchpercent="83" state="translated" state-qualifier="fuzzy-match">Typ składnika kosztów = Inny; Inny typ kosztu = Lokalizacja</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>A combination of the <bpt id="p1">**</bpt>Other<ept id="p1">**</ept> cost component type and the <bpt id="p2">**</bpt>Location<ept id="p2">**</ept> other cost type is used to define non-shipping costs for a group of locations or an individual location.</source><target logoport:matchpercent="0" state="translated">Kombinacja typu składnika kosztów <bpt id="p1">**</bpt>Inny<ept id="p1">**</ept> oraz innego typu kosztu <bpt id="p2">**</bpt>Lokalizacja<ept id="p2">**</ept> służy do definiowania kosztów niezwiązanych z wysyłką dla grupy lokalizacji lub pojedynczej lokalizacji.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>You must set up the following fields for this combination:</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Dla tej kombinacji musisz skonfigurować następujące pola:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source><bpt id="p1">**</bpt>Cost factor<ept id="p1">**</ept> – Enter a unique identifier for the cost factor.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Współczynnik kosztu<ept id="p1">**</ept> — umożliwia wprowadzenie unikatowego identyfikatora współczynnika kosztu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source><bpt id="p1">**</bpt>Description<ept id="p1">**</ept> – Enter the name and description of the cost factor.</source>
        <target logoport:matchpercent="78" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Opis<ept id="p1">**</ept> — umożliwia wprowadzenie nazwy i opisu współczynnika kosztu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source><bpt id="p1">**</bpt>Start date<ept id="p1">**</ept> and <bpt id="p2">**</bpt>End date<ept id="p2">**</ept> – You can use these fields to limit the cost factor for a specific date range.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Data rozpoczęcia<ept id="p1">**</ept> i <bpt id="p2">**</bpt>Data zakończenia<ept id="p2">**</ept> — za pomocą tych pól możesz ograniczyć współczynnik kosztu do określonego zakresu dat.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>If you leave these fields blank, the cost factor is valid for an indefinite period.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Jeśli zostawisz te pola puste, współczynnik kosztu będzie prawidłowy w nieskończonym okresie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source><bpt id="p1">**</bpt>Active<ept id="p1">**</ept> – Indicate whether the cost factor is active.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Aktywny<ept id="p1">**</ept> — umożliwia wskazanie, czy dany współczynnik kosztu jest aktywny.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>The DOM considers only active cost factors that are associated with the fulfillment profile.</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Funkcja zarządzania zamówieniami rozdzielonymi uwzględnia tylko aktywne współczynniki kosztów, które są skojarzone z profilem realizacji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source><bpt id="p1">**</bpt>Fulfillment group<ept id="p1">**</ept> – Specify the group of locations that the non-shipping cost is defined for.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Grupa realizacji<ept id="p1">**</ept> — umożliwia określenie grupy lokalizacji, dla której jest definiowany koszt niezwiązany z wysyłką.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source><bpt id="p1">**</bpt>Fulfillment location<ept id="p1">**</ept> – Specify the location that the non-shipping cost is defined for.</source><target logoport:matchpercent="81" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Lokalizacja realizacji<ept id="p1">**</ept> — umożliwia określenie lokalizacji, dla której jest definiowany koszt niezwiązany z wysyłką.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>You can't specify a fulfillment group and a fulfillment location on the same line for location-based calculation criteria.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">W przypadku kryteriów obliczania opartych na lokalizacji nie możesz określić w tym samym wierszu grupy realizacji i lokalizacji realizacji.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source><bpt id="p1">**</bpt>Cost<ept id="p1">**</ept> – Specify the cost value for a non-shipping cost at the fulfillment group level or fulfillment location level.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Koszt<ept id="p1">**</ept> — umożliwia określenie wartości kosztu dla kosztu niezwiązanego z wysyłką na poziomie grupy realizacji lub lokalizacji realizacji.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>For DOM to consider these costs when it's run, you must add the cost factor to the relevant fulfillment profile.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Aby funkcja zarządzania zamówieniami rozdzielonymi mogła uwzględniać te koszty, gdy zostanie uruchomiona, musisz dodać współczynnik kosztu do odpowiedniego profilu realizacji.</target>
        </trans-unit>
      </group>
    </body>
  </file>
</xliff>