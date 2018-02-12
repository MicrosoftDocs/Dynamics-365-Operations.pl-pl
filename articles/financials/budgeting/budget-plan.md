---
title: "Planowanie budżetu"
description: "Celem tego warsztatu jest praktyczne zaprezentowanie aktualizacji funkcji programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition w obszarze planowania budżetu. Zilustrowaliśmy przykład krótkiej konfiguracji modułu planowania budżetu oraz pokazaliśmy, jak przy użyciu tej konfiguracji można planować budżet.  Ten warsztat dotyczy głównie następujących procesów lub zadań biznesowych:  - Tworzenie hierarchii organizacyjnej na potrzeby planowania budżetu i konfigurowania zabezpieczeń użytkownika  - Definiowanie scenariuszy planu budżetu, kolumn planu budżetu, układów i szablonów programu Excel  - Tworzenie i aktywacja procesu planowania budżetu  - Tworzenie dokumentu planu budżetu poprzez pobieranie wartości rzeczywistych z księgi głównej  - Używanie alokacji do korygowania danych dokumentu planu budżetu  - Edytowanie danych dokumentu planu budżetu w programie Excel"
author: twheeloc
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c6440591f847cbbb6be352270e3629a49d71598e
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="budget-planning"></a>Planowanie budżetu

[!include[banner](../includes/banner.md)]


Celem tego warsztatu jest praktyczne zaprezentowanie aktualizacji funkcji programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition w obszarze planowania budżetu. Zilustrowaliśmy przykład krótkiej konfiguracji modułu planowania budżetu oraz pokazaliśmy, jak przy użyciu tej konfiguracji można planować budżet.  Ten warsztat dotyczy głównie następujących procesów lub zadań biznesowych:  - Tworzenie hierarchii organizacyjnej na potrzeby planowania budżetu i konfigurowania zabezpieczeń użytkownika  - Definiowanie scenariuszy planu budżetu, kolumn planu budżetu, układów i szablonów programu Excel  - Tworzenie i aktywacja procesu planowania budżetu  - Tworzenie dokumentu planu budżetu poprzez pobieranie wartości rzeczywistych z księgi głównej  - Używanie alokacji do korygowania danych dokumentu planu budżetu  - Edytowanie danych dokumentu planu budżetu w programie Excel 

<a name="prerequisites"></a>Wymagania wstępne 
------------------

Aby skorzystać z tego samouczka, musisz uzyskać dostęp do środowiska Finance and Operations z danymi demonstracyjnymi Contoso i mieć uprawnienia administratora w używanym wystąpieniu. Podczas tego warsztatu nie należy używać trybu prywatnego przeglądarki — w razie potrzeby wyloguj się ze wszystkich innych kont w przeglądarce i zaloguj się w programie Finance and Operations przy użyciu poświadczeń administratora. Podczas logowania się w programie Finance and Operations **musisz** zaznaczyć pole wyboru „Nie wylogowuj mnie”. Spowoduje to utworzenie trwałego pliku cookie potrzebnego w aplikacji Excel. Jeśli zalogujesz się w programie Finance and Operations przy użyciu przeglądarki innej niż IE, zobaczysz monit o zalogowanie się do aplikacji Excel. Po kliknięciu przycisku Zaloguj się w aplikacji Excel zostanie wyświetlone wyskakujące okienko i podczas logowania się **TRZEBA** zaznaczyć pole wyboru Nie wylogowuj mnie. Jeśli kliknięcie przycisku Zaloguj się w aplikacji Excel nie spowoduje wyświetlenia okienka, wyczyść pamięć podręczną plików cookie aplikacji IE.

## <a name="scenario-overview"></a>**Omówienie scenariusza**
Julia pracuje na stanowisku menedżera finansów w firmie Contoso Entertainment Systems w Niemczech (DEMF). Gdy nadchodzi rok obrachunkowy 2016, Julia musi skonfigurować budżet firmy na nadchodzący rok. Przygotowanie budżetu wygląda następująco:

1.  Julia używa kwot rzeczywistych z poprzedniego roku jako punktu początkowego tworzenia budżetu.
2.  W oparciu o wartości rzeczywiste poprzedniego roku tworzy oszacowania dla 12 miesięcy w nadchodzącym roku
3.  Julia sprawdza budżet z dyrektorem finansowym. Następnie wprowadza niezbędne korekty planu budżetu i kończy przygotowanie budżetu.

Schemat konfiguracji planowania budżetu dla scenariusza wygląda następująco:

![Schemat konfiguracji planowania budżetu](./media/screenshot1-300x152.png)

Julia używa następującego szablonu programu Excel do przygotowania budżetu:

[![Szablon programu Excel](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

## <a name="exercise-1-configuration"></a>Ćwiczenie 1: Konfiguracja

### <a name="task-1-create-organizational-hierarchy"></a>**Zadanie 1: Tworzenie hierarchii organizacyjnej**
Cały proces budżetowania odbywa się w dziale finansów, dlatego Julia musi utworzyć bardzo prostą hierarchię organizacji, składającą się tylko z działu finansów. 1.1. Przejdź do okna Hierarchie organizacyjne (Administrowanie organizacją &gt; Organizacje &gt; Hierarchie organizacyjne) i kliknij przycisk Nowy.

![Hierarchia organizacyjna](./media/screenshot3.png) 

1.2. Wpisz nazwę dla hierarchii organizacyjnej, a następnie kliknij przycisk Przypisz cel.

[![Nazwa](./media/screenshot4.png)](./media/screenshot4.png) 

1.3. Wybierz cel planowania budżetu, kliknij przycisk Dodaj, a następnie przypisz nowo utworzoną hierarchię organizacyjną: 

[![Przypisywanie celu](./media/screenshot5.png)](./media/screenshot5.png)

1.4. Powtórz powyższy krok w celu wprowadzenia przyczyny zabezpieczeń do hierarchii organizacyjnej. Po zakończeniu zamknij formularz.

[![Organizacja zabezpieczeń](./media/screenshot6.png)](./media/screenshot6.png)

1.5. W formularzu hierarchii organizacyjnej kliknij przycisk Wyświetl. Kliknij przycisk Edytuj w projektancie hierarchii i utwórz hierarchię, klikając przycisk Wstaw.

[![Wstawianie](./media/screenshot7.png)](./media/screenshot7.png) 

1.6. Wybierz dział finansowy dla hierarchii budżetowania. 

[![Finanse](./media/screenshot8.png)](./media/screenshot8.png)

1.7. Po zakończeniu kliknij przycisk Publikuj i zamknij. Wybierz 1/1/2015 jako datę rozpoczęcia publikowania hierarchii.

[![Data obowiązywania](./media/screenshot9.png)](./media/screenshot9.png)

### <a name="task-2-configure-user-security"></a>Zadanie 2: Konfigurowanie zabezpieczeń użytkownika
Planowanie budżetu używa specjalnych zasad zabezpieczeń do konfigurowania dostępu do danych planów budżetu. Julia musi przyznać sobie dostęp do planów budżetu działu finansowego. 

2.1. Przełącz się do kontekstu firmy DEMF. 


2.2. Wybierz kolejno opcje Budżetowanie &gt; Ustawienia &gt; Planowanie budżetu &gt; Konfiguracja planowania budżetu. Na karcie Parametry ustaw wartość Model zabezpieczeń jako Na podstawie organizacji zabezpieczeń. 

[![Parametry](./media/screenshot11.png)](./media/screenshot11.png) 

2.3. Wybierz kolejno opcje Administrowanie systemem &gt; Użytkownicy &gt; Użytkownicy. Przyznaj użytkownikowi rolę administracyjną (Julia Funderburk) zarządzania budżetem. 

[![Menedżer budżetu](./media/screenshot12.png)](./media/screenshot12.png) 

2.4. Wskaż rolę użytkownika i kliknij przycisk Przypisz organizacje. 

[![Przypisywanie organizacji](./media/screenshot13.png)](./media/screenshot13.png)

2.5. Wybierz opcję „Udziel dostępu do określonych organizacji”. Wskaż hierarchię organizacyjną utworzoną w pierwszym kroku. Wybierz węzeł Finanse i kliknij przycisk Udziel dostępu wraz z podrzędnymi. 

***Ważne!*** *Upewnij się, że znajdujesz się w kontekście firmy DEMF podczas wykonywania tego zadania, ponieważ zabezpieczenia na poziomie organizacji są stosowane do firmy.* 

[![Udzielanie dostępu](./media/screenshot14.png)](./media/screenshot14.png)

### <a name="task-3-create-scenarios"></a>Zadanie 3: Tworzenie scenariuszy
3.1. Wybierz kolejno opcje Budżetowanie &gt; Ustawienia &gt; Planowanie budżetu &gt; Konfiguracja planowania budżetu. Na stronie scenariuszy zwróć uwagę na scenariusze, które wykorzystasz w dalszej części ćwiczenia: Wartości rzeczywiste w poprzednim roku i Zabudżetowane. 

*Uwaga: możesz utworzyć nowe scenariusze i użyć ich zamiast proponowanych.* 

[![Nowe scenariusze](./media/screenshot15.png)](./media/screenshot15.png) 

*Uwaga: Ze względu na to, że do przygotowania budżetu Julia nie używa procesu formalnego zatwierdzenia, w tym ćwiczeniu pominiemy konfigurację przepływów pracy, etapów i etapów przepływów pracy, a użyjemy istniejącej konfiguracji przepływu pracy automatycznego zatwierdzania. Ta konfiguracja przepływu pracy jest omówiona w dodatku.*

### <a name="task-4-create-budget-plan-columns"></a>Zadanie 4: Tworzenie kolumn planu budżetu
Kolumny planu budżetu zawierają wartości pieniężne lub ilości i można je umieścić w układzie dokumentu planu budżetu. W naszym przykładzie musimy utworzyć kolumnę dla Wartości rzeczywistych w poprzednim roku oraz 12 kolumn dla wszystkich miesięcy w budżetowanym roku. Można utworzyć kolumny albo po prostu klikając przycisk Dodaj i wypełniając wartości lub z pomocą jednostki danych. W tym ćwiczeniu użyjemy jednostki danych do wstawienia wartości. 

4.1. W oknie Budżetowanie &gt; Ustawienia &gt; Planowanie budżetu &gt; Konfiguracja planowania budżetu otwórz stronę Kolumny. Kliknij przycisk Office w prawym górnym rogu formularza i wskaż opcję Kolumny (niefiltrowane). 

[![Kolumny niefiltrowane](./media/screenshot16.png)](./media/screenshot16.png) 

4.2. System otworzy skoroszyt programu Excel, który zostanie wykorzystany do wprowadzenia wartości. Jeśli zostanie wyświetlony monit, kliknij kolejno opcje Włącz edytowanie i Zaufaj tej aplikacji. 

[![Włączanie edytowania](./media/screenshot18.png)](./media/screenshot18.png) 

[![Opcja Zaufaj tej aplikacji](./media/screenshot17.png)](./media/screenshot17.png)

4.3. Będziemy potrzebować więcej kolumn do wprowadzenia wartości. Kliknij opcję Projekt w okienku po prawej stronie, aby dodać kolumny do siatki: 

[![Projekt](./media/screenshot19.png)](./media/screenshot19.png) 

4.4. Kliknij przycisk z małym ołówkiem obok opcji Kolumny planu, aby zobaczyć kolumny, które można dodać do siatki. 

[![Edytowanie](./media/screenshot20.png)](./media/screenshot20.png) 

4.5. Kliknij dwukrotnie każde dostępne pole, aby dodać je do wybranych pól, a następnie kliknij opcję Aktualizuj. 

![Aktualizowanie](./media/screenshot21.png)](./media/screenshot21.png) 

4.6. W tabeli programu Excel dodaj wszystkie kolumny, które trzeba utworzyć. Użyj funkcji automatycznego wypełniania w programie Excel, aby szybko dodać wiersze. Upewnij się, że wiersze są dodawane jako część tabeli (kiedy przewiniesz w pionie, powinny być wyświetlane nagłówki kolumn w górnej części siatki). 

[![Automatyczne wypełnianie](./media/screenshot22.png)](./media/screenshot22.png) 

4.7. Wróć do programu Finance and Operations i odśwież stronę. Opublikowane wartości będą wyświetlane w programie Finance and Operations. 

[![Odśwież](./media/screenshot23.png)](./media/screenshot23.png)

### <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>Zadanie 5: Utwórz szablony i układy dokumentów planu budżetu
Układ określa, jak siatka wierszy dokumentu planu budżetu będzie wyglądać, gdy użytkownik otworzy dokument planu budżetu. Istnieje również możliwość przełączenia układu dokumentu planu budżetu, żeby zobaczyć te same dane pod różnymi kątami. Teraz, kiedy Julia ma już zdefiniowane kolumny, które zostaną wykorzystane w dokumencie planu budżetu, musi utworzyć układ dokumentu planu budżetu, który będzie wyglądał podobnie do tabeli programu Excel wykorzystywanej do utworzenia danych budżetu (zobacz sekcję Omówienie scenariusza w tym ćwiczeniu). 

5.1. W oknie Budżetowanie &gt; Ustawienia &gt; Planowanie budżetu &gt; Konfiguracja planowania budżetu otwórz stronę Układy. Utwórz nowy układ dla wpisu miesięcznego budżetu:

-   Wybierz zestaw wymiarów konta głównego i jednostek biznesowych, które zostaną uwzględnione w układzie KG + JB.
-   Umieść wszystkie kolumny planu budżetu utworzone w poprzednim kroku w sekcji Elementy. Włącz edycję wszystkich elementów poza Wartościami rzeczywistymi w poprzednim roku.
-   Kliknij przycisk Opisy, aby wybrać, które wymiary finansowe mają pokazywać opisy w siatce.

[![Opisy](./media/screenshot24.png)](./media/screenshot24.png) 

Na podstawie definicji układu planu budżetu możemy utworzyć szablon programu Excel, który będzie wykorzystywany jako alternatywny sposób edytowania danych budżetu. Ponieważ szablon programu Excel musi pasować do definicji układu planu budżetu, nie będzie można edytować układu planu budżetu po wygenerowaniu szablonu programu Excel. Dlatego to zadanie należy wykonać po zdefiniowaniu wszystkich elementów układu. 

5.2. W układzie utworzonym w kroku w 5.1. kliknij kolejno opcje Szablon &gt; Generuj. Potwierdź komunikat ostrzegawczy. Aby wyświetlić szablon, kliknij kolejno opcje Szablon &gt; Widok. 

*Uwaga: Pamiętaj o wybraniu opcji „Zapisz jako” i wskazaniu miejsca, w którym chcesz zapisać szablon, aby potem go edytować. W przypadku wybrania w oknie dialogowym opcji „Otwórz” bez zapisywania zmiany wprowadzone w pliku nie zostaną zachowane po jego zamknięciu.* 
[![Widok szablonu](./media/screenshot25.png)](./media/screenshot25.png) 

5.3. &lt; Opcjonalny krok&gt; Zmodyfikuj szablon programu Excel, tak aby był bardziej przyjazny użytkownikowi — dodaj formuły sumy, pola nagłówków, formatowanie itd. Zapisz zmiany i załaduj plik do układu planu budżetu, klikając kolejno opcje Układ &gt; Przekaż. [![Przekazywanie](./media/screenshot26.png)](./media/screenshot26.png)

### <a name="task-6-create-a-budget-planning-process"></a>Zadanie 6: Utwórz proces planowania budżetu
Julia musi utworzyć i aktywować nowy proces planowania budżetu, uwzględniając całą powyższą konfigurację, aby rozpocząć wprowadzanie planów budżetu. Proces planowania budżetu określa, jakie organizacje budżetowania, przepływ pracy, układy i szablony będą używane do tworzenia planów budżetu. 

6.1. Przejdź do okna Budżetowanie &gt; Ustawienia &gt; Planowanie budżetu &gt; Proces planowania budżetu i utwórz nowy rekord.

-   Proces planowania budżetu — budżetowanie DEMF; rok obrachunkowy 2016
-   Cykl budżetu — rok obrachunkowy 2016
-   Księga — DEMF
-   Domyślna struktura konta — Produkcja P&L
-   Hierarchia organizacyjna — pobierz hierarchię utworzoną na początku ćwiczeń
-   Przepływ pracy planowania budżetu — przypisz przepływ pracy automatycznego zatwierdzania dla działu finansów
-   W szablonach i regułach etapu planowania budżetu dla każdego etapu przepływu pracy planowania budżetu określ, czy dozwolone jest dodawanie i modyfikowanie wierszy oraz wybierz układ stosowany domyślnie.

*Uwaga: można tworzyć układy dokumentów dodatkowych i ustawiać tak, aby były dostępne na etapie przepływu pracy planowania budżetu. W tym celu kliknij przycisk Alternatywne układy.* 

[![Alternatywne układy](./media/screenshot27.png)](./media/screenshot27.png) 

6.2. Wybierz kolejno opcje Akcje &gt; Aktywuj, aby włączyć ten przepływ pracy planowania budżetu. 

[![Aktywowanie](./media/screenshot28.png)](./media/screenshot28.png)

## <a name="exercise-2-process-simulation"></a>Ćwiczenie 2: Symulacja procesu

### <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>Zadanie 7: Generowanie danych początkowych dla planu budżetu z księgi głównej
7.1. Przejdź do okna Budżetowanie &gt; Okresowo &gt; Generowanie planu budżetu z księgi głównej. Wprowadź parametry przetwarzania okresowego i kliknij przycisk Generuj. 

[![Generowanie](./media/screenshot29.png)](./media/screenshot29.png) 

7.2. Przejdź do okna Budżetowanie &gt; Plany budżetu, aby znaleźć plan budżetu utworzony przez proces generowania. 

[![Plan budżetu](./media/screenshot30.png)](./media/screenshot30.png) 

7.3. Otwórz szczegóły dokumentu, klikając hiperłącze numeru dokumentu. Plan budżetu zostanie wyświetlony jako zdefiniowany w układzie utworzonym podczas tego ćwiczenia. 

[![Wyświetlanie planu budżetu](./media/screenshot31.png)](./media/screenshot31.png)

### <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>Zadanie 8: Utwórz budżet bieżącego roku w oparciu o wartości rzeczywiste w poprzednim roku
W planie budżetu można użyć metody alokacji, aby łatwo skopiować informacje o planie budżetu z jednego scenariusza do drugiego, podzielić je na okresy i alokować do wymiarów. Użyjemy alokacji do utworzenia budżetu na bieżący rok na podstawie wartości rzeczywistych z poprzedniego roku. 

8.1. Pobierz wszystkie wiersze siatki dokumentu planu budżetu, a następnie kliknij przycisk alokowania budżetu. 

[![Wszystkie wiersze](./media/screenshot32.png)](./media/screenshot32.png) 

8.2. Wybierz metodę alokacji, klucz okresu oraz scenariusze źródłowy i docelowy, a następnie kliknij przycisk Alokuj 

[![Alokowanie](./media/screenshot33.png)](./media/screenshot33.png)

Kwoty rzeczywiste poprzedniego roku zostaną skopiowane do budżetu bieżącego roku i przydzielone między okresy za pomocą klucza okresu Krzywa sprzedaży. 

[![Krzywa sprzedaży](./media/screenshot34.png)](./media/screenshot34.png)

### <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>Zadanie 9: Korygowanie planu budżetu przy użyciu programu Excel i kończenie pracy nad dokumentem
9.1. Kliknij przycisk Arkusz, aby otworzyć zawartość dokumentu w programie Excel.

[![Program Excel](./media/screenshot35.png)](./media/screenshot35.png)

9.2. Gdy skoroszyt programu Excel zostanie wyświetlony, skoryguj liczby w dokumencie planu budżetu i kliknij przycisk Publikuj.

[![Publikuj](./media/screenshot36.png)](./media/screenshot36.png)

9.3. Wróć do dokumentu planu budżetu w programie Finance and Operations. Kliknij kolejno opcje Przepływ pracy &gt; Prześlij, aby automatycznie zatwierdzić dokument.

[![Automatyczne zatwierdzanie](./media/screenshot37.png)](./media/screenshot37.png) 

Po zakończeniu przepływu pracy etap dokumentu planu budżetu zmieni się na Zatwierdzony. [![Zatwierdzone](./media/screenshot38.png)](./media/screenshot38.png)

## <a name="appendix"></a>Dodatek

### <a name="auto-approve-workflow-configuration"></a>Konfiguracja przepływu pracy automatycznego zatwierdzania

A. Budżetowanie &gt; Ustawienia &gt; Planowanie budżetu &gt; Przepływy pracy budżetowania Utwórz nowy przepływ pracy przy użyciu szablonu Przepływy pracy planowania budżetu

[![Tworzenie nowego przepływu pracy.](./media/screenshot39.png)](./media/screenshot39.png)

Ten przepływ pracy będzie zawierał tylko jedno zadanie — Przejście do etapu planu budżetu. 

[![Przejście do etapu planu budżetu](./media/screenshot40.png)](./media/screenshot40.png) 

Zapisz i aktywuj przepływ pracy. 

B. Wybierz kolejno opcje Budżetowanie &gt; Ustawienia &gt; Planowanie budżetu &gt; Konfiguracja planowania budżetu. Na karcie Etapy utwórz 2 etapy — Początkowy i Przesłano. 

[![Etapy Początkowy i Przesłano](./media/screenshot41.png)](./media/screenshot41.png)

C. Wybierz kolejno opcje Budżetowanie &gt; Ustawienia &gt; Planowanie budżetu &gt; Konfiguracja planowania budżetu. Na karcie Etapy przepływu pracy skojarz przepływ pracy automatycznego zatwierdzania utworzony w kroku A z etapami Początkowy i Przesłano. 

[![Budżetowanie i planowanie budżetu](./media/screenshot42.png)](./media/screenshot42.png)  




