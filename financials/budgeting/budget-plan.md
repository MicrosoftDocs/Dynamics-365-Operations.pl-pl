---
title: "Planowanie budżetu"
description: "Celem tego ćwiczenia jest zapewniają widok z przewodnikiem Microsoft Dynamics 365 dla operacji aktualizacji funkcji w obszarze planowania budżetu. Zilustrowaliśmy przykład krótkiej konfiguracji modułu planowania budżetu oraz pokazaliśmy, jak przy użyciu tej konfiguracji można planować budżet.  To laboratorium skupi się w szczególności na następujących procesów biznesowych oraz zadań--tworzenie hierarchii organizacyjnej budżetu, planowania i konfigurowania zabezpieczeń użytkownika - Definiowanie scenariuszy planu budżetu, kolumn planu budżetu, układy i szablony programu Excel — tworzenie i aktywacja budżetu planowania procesu - Tworzenie planu budżetu przez ciągnięcie wartości rzeczywiste z księgi głównej - korzystanie z alokacji do ustawiania danych dokumentu planu budżetu - edycji danych planu budżetu dokumentu w programie Excel"
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 81b44aa7af3a05ebc28963f406fab98bfbbb340d
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning"></a>Planowanie budżetu

Celem tego ćwiczenia jest zapewniają widok z przewodnikiem Microsoft Dynamics 365 dla operacji aktualizacji funkcji w obszarze planowania budżetu. Zilustrowaliśmy przykład krótkiej konfiguracji modułu planowania budżetu oraz pokazaliśmy, jak przy użyciu tej konfiguracji można planować budżet.  To laboratorium skupi się w szczególności na następujących procesów biznesowych oraz zadań--tworzenie hierarchii organizacyjnej budżetu, planowania i konfigurowania zabezpieczeń użytkownika - Definiowanie scenariuszy planu budżetu, kolumn planu budżetu, układy i szablony programu Excel — tworzenie i aktywacja budżetu planowania procesu - Tworzenie planu budżetu przez ciągnięcie wartości rzeczywiste z księgi głównej - korzystanie z alokacji do ustawiania danych dokumentu planu budżetu - edycji danych planu budżetu dokumentu w programie Excel 

<a name="prerequisites"></a>Wymagania wstępne 
------------------

Ten samouczek musisz dostęp do 365 Dynamics dla środowiska operacji z danych demonstracyjnych Contoso, obsługiwane jako administrator na wystąpienie. Nie należy używać w prywatnej trybu przeglądarki dla tego laboratorium - Wyrejestruj się z żadnego innego konta w przeglądarce, w razie potrzeby i zaloguj się Dynamics 365 o poświadczenia administratora operacji. Podczas logowania do systemu Dynamics 365 dla operacji, można **musi** zaznacz pole wyboru "Nie wylogowuj mnie". Spowoduje to utworzenie trwałego pliku cookie potrzebnego w aplikacji Excel. Jeśli użytkownik zaloguje się do 365 Dynamics dla operacji przy użyciu innej przeglądarki niż IE, następnie zostanie wyświetlony monit Zaloguj się w aplikacji Excel. Po kliknięciu przycisku Zaloguj się w aplikacji Excel zostanie wyświetlone wyskakujące okienko i podczas logowania się **TRZEBA** zaznaczyć pole wyboru Nie wylogowuj mnie. Jeśli kliknięcie przycisku Zaloguj się w aplikacji Excel nie spowoduje wyświetlenia okienka, wyczyść pamięć podręczną plików cookie aplikacji IE.

## <a name="scenario-overview"></a>**Scenario overview**
Julia pracuje na stanowisku menedżera finansów w firmie Contoso Entertainment Systems w Niemczech (DEMF). Gdy nadchodzi rok obrachunkowy 2016, Julia musi skonfigurować budżet firmy na nadchodzący rok. Przygotowanie budżetu wygląda następująco:

1.  Julia używa kwot rzeczywistych z poprzedniego roku jako punktu początkowego tworzenia budżetu.
2.  W oparciu o wartości rzeczywiste poprzedniego roku tworzy oszacowania dla 12 miesięcy w nadchodzącym roku
3.  Julia sprawdza budżet z dyrektorem finansowym. Następnie wprowadza niezbędne korekty planu budżetu i kończy przygotowanie budżetu.

Schemat konfiguracji dla scenariusza planowania budżetu wygląda następująco:

![Screenshot1](./media/screenshot1-300x152.png)

Julia używa następującego szablonu programu Excel, aby przygotować budżet:

[![](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

<a name="exercise-1-configuration"></a>Ćwiczenie 1: Konfiguracja
=========================

## <a name="task-1-create-organizational-hierarchy"></a>**Zadanie 1: Tworzenie hierarchii organizacyjnej**
Cały proces budżetowania odbywa się w dziale finansów, dlatego Julia musi utworzyć bardzo prostą hierarchię organizacji, składającą się tylko z działu finansów. 1.1. Przejdź do hierarchii organizacji (Administrowanie organizacją &gt;organizacji &gt;hierarchii organizacyjnej) i kliknij przycisk Nowy

![Screenshot3](./media/screenshot3.png) 

1.2. Wpisz nazwę dla hierarchii organizacyjnej i kliknij przycisk Przypisywanie celu

[![Screenshot4](./media/screenshot4.png)](./media/screenshot4.png) 

1.3. Wybierz cel Planowanie budżetu, kliknij przycisk Dodaj i przypisywania nowo utworzonej hierarchii organizacyjnej: 

[![Screenshot5](./media/screenshot5.png)](./media/screenshot5.png)

1.4. Powtórz powyższy krok w celu wprowadzenia przyczyny zabezpieczeń do hierarchii organizacyjnej. Po zakończeniu zamknij formularz.

[![Screenshot6](./media/screenshot6.png)](./media/screenshot6.png)

1.5. W formularzu hierarchii organizacyjnej kliknij przycisk Wyświetl. Kliknij przycisk Edytuj w projektancie hierarchii i utwórz hierarchię, klikając przycisk Wstaw.

[![Screenshot7](./media/screenshot7.png)](./media/screenshot7.png) 

1.6. Wybierz dział finansowy dla hierarchii budżetowania. 

[![Screenshot8](./media/screenshot8.png)](./media/screenshot8.png)

1.7. Po zakończeniu kliknij przycisk Publikuj i zamknij. Wybierz 1/1/2015 jako datę rozpoczęcia publikowania hierarchii.

[![Screenshot9](./media/screenshot9.png)](./media/screenshot9.png)

## <a name="task-2-configure-user-security"></a>Zadanie 2: Konfigurowanie zabezpieczeń użytkownika
Planowanie budżetu używa specjalnych zasad zabezpieczeń do konfigurowania dostępu do danych planów budżetu. Julia musi przyznać sobie dostęp do planów budżetu działu finansowego. 2.1. Przełącz się na kontekst firmy DEMF: [![Screenshot10](./media/screenshot10.png)](./media/screenshot10.png) 2.2. Przejdź do budżetowania &gt;instalacji &gt;planowania budżetu &gt;Konfiguracja planowania budżetu. Na karcie Parametry ustawioną wartość model zabezpieczeń oparty na organizacji bezpieczeństwa [![Screenshot11](./media/screenshot11.png)](./media/screenshot11.png) 2.3. Przejdź do administracji systemu &gt;użytkowników &gt;użytkowników. Przyznaj użytkownikowi rolę administracyjną (Julia Funderburk) zarządzania budżetem. [![Screenshot12](./media/screenshot12.png)](./media/screenshot12.png) 2.4. Wybierz rolę użytkownika i kliknij przycisk Przypisz organizacje [![Screenshot13](./media/screenshot13.png)](./media/screenshot13.png)2.5. Wybierz opcję „Udziel dostępu do określonych organizacji”. Wskaż hierarchię organizacyjną utworzoną w pierwszym kroku. Wybierz węzeł finansów i kliknij dotacji klawiszem dzieci ***ważne!*** *-Upewnij się, że w kontekście podmiot prawny DEMF podczas wykonywania tego zadania, jak zabezpieczeń organizacji jest stosowane dla każdej firmy*[![Screenshot14](./media/screenshot14.png)](./media/screenshot14.png)

## <a name="task-3-create-scenarios"></a>Zadanie 3: Tworzenie scenariuszy
3.1. Przejdź do budżetowania&gt;instalacji &gt;planowania budżetu &gt;Konfiguracja planowania budżetu. Na stronie scenariuszy zwróć uwagę na scenariusze, które wykorzystasz w dalszej części ćwiczenia: Wartości rzeczywiste w poprzednim roku i Zabudżetowane. *Uwaga: możesz utworzyć nowe scenariusze i użyć ich zamiast proponowanych.* [![Screenshot15](./media/screenshot15.png)](./media/screenshot15.png)*Uwaga: jak Julia nie używa formalne zatwierdzenie procesu przygotowania budżetu, firma Microsoft będzie pominąć etapy przepływy pracy i etapów przepływu pracy w tym laboratorium ustawień i użyje istniejące ustawienia Auto – Zatwierdź przepływ pracy. Patrz dodatek dla tej konfiguracji przepływu pracy.*

## <a name="task-4-create-budget-plan-columns"></a>Zadanie 4: Tworzenie kolumn planu budżetu
Kolumny planu budżetu zawierają wartości pieniężne lub ilości i można je umieścić w układzie dokumentu planu budżetu. W naszym przykładzie musimy utworzyć kolumnę dla Wartości rzeczywistych w poprzednim roku oraz 12 kolumn dla wszystkich miesięcy w budżetowanym roku. Można utworzyć kolumny albo po prostu klikając przycisk Dodaj i wypełniając wartości lub z pomocą jednostki danych. W tym ćwiczeniu użyjemy jednostki danych do wstawienia wartości. 4.1. W module Budżetowanie&gt;instalacji &gt;planowania budżetu &gt;budżetu planowania konfiguracji otwarte strony kolumny. Kliknij przycisk pakietu Office, w prawym górnym rogu formularza i wybierz kolumny (niefiltrowane) [![Screenshot16](./media/screenshot16.png)](./media/screenshot16.png) 4.2. System otworzy skoroszyt programu Excel, który zostanie wykorzystany do wprowadzenia wartości. Jeśli pojawi się monit, kliknij przycisk Włącz edytowanie i ufać tej aplikacji [![Screenshot18](./media/screenshot18.png)](./media/screenshot18.png)[![Screenshot17](./media/screenshot17.png)](./media/screenshot17.png) 4.3. Potrzebujemy więcej kolumn, aby wypełnić wartości. Kliknij polecenie Projekt w okienku po prawej stronie, aby dodać kolumny do siatki: [![Screenshot19](./media/screenshot19.png)](./media/screenshot19.png) 4.4. Kliknij mały przycisk ołówka obok PlanColumns, aby wyświetlić dostępne kolumny do dodania do siatki [![Screenshot20](./media/screenshot20.png)](./media/screenshot20.png) 4.5. Kliknij dwukrotnie każde dostępne pole, aby dodać je do pola wybrane i kliknij przycisk Aktualizuj, [![Screenshot21](./media/screenshot21.png)](./media/screenshot21.png) 4.6. W tabeli programu Excel dodaj wszystkie kolumny, które trzeba utworzyć. Użyj funkcji automatycznego wypełniania w programie Excel, aby szybko dodać wiersze. Upewnij się, wiersze są dodawane jako część tabeli (używając przewijania pionowego, można wyświetlić nagłówki kolumn w górnej części siatki) [![Screenshot22](./media/screenshot22.png)](./media/screenshot22.png) 4.7. Wróć do 365 Dynamics dla operacji i Odśwież stronę. Opublikowane wartości będą wyświetlane w usłudze Dynamics 365 dla operacji. [![Screenshot23](./media/screenshot23.png)](./media/screenshot23.png)

## <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>Zadanie 5: Utwórz szablony i układy dokumentów planu budżetu
Układ określa, jak siatka wierszy dokumentu planu budżetu będzie wyglądać, gdy użytkownik otworzy dokument planu budżetu. Istnieje również możliwość przełączenia układu dokumentu planu budżetu, żeby zobaczyć te same dane pod różnymi kątami. Teraz, kiedy Julia ma już zdefiniowane kolumny, które zostaną wykorzystane w dokumencie planu budżetu, musi utworzyć układ dokumentu planu budżetu, który będzie wyglądał podobnie do tabeli programu Excel wykorzystywanej do utworzenia danych budżetu (zobacz sekcję Omówienie scenariusza w tym ćwiczeniu) 5.1. W module Budżetowanie&gt;instalacji &gt;planowania budżetu &gt;budżetu planowania konfiguracji otwartej układy strony. Utwórz nowy układ dla wpisu miesięcznego budżetu:

-   Wybierz zestaw wymiarów konta głównego i jednostek biznesowych, które zostaną uwzględnione w układzie KG + JB.
-   Umieść wszystkie kolumny planu budżetu utworzone w poprzednim kroku w sekcji Elementy. Włącz edycję wszystkich elementów poza Wartościami rzeczywistymi w poprzednim roku.
-   Kliknij przycisk Opisy, aby wybrać, które wymiary finansowe mają pokazywać opisy w siatce.

[![Screenshot24](./media/screenshot24.png)](./media/screenshot24.png) w oparciu o budżet plan definicji układu, możesz stworzyć szablonu programu Excel do użycia jako alternatywny sposób edycji danych budżetu. Ponieważ szablon programu Excel musi pasować do definicji układu planu budżetu, nie będzie można edytować układu planu budżetu po wygenerowaniu szablonu programu Excel. Dlatego to zadanie należy wykonać po zdefiniowaniu wszystkich elementów układu. 5.2. W układzie utworzone w 5.1. Krok, kliknij przycisk Szablon &gt;Generuj. Potwierdź komunikat ostrzegawczy. Aby wyświetlić szablon, kliknij przycisk Szablon &gt;widok. *Uwaga: Upewnij się wybrać "Zapisz jako" i wybierz miejsce przechowywania szablonu pozwoli go edytować. Jeśli użytkownik wybierze "Otwarte" okno dialogowe bez zapisywania, zmiany dokonane w pliku nie zostaną zachowane po zamknięciu pliku.* [![Screenshot25](./media/screenshot25.png)](./media/screenshot25.png) 5.3. &lt;Opcjonalny krok&gt; szablon modyfikować programu Excel, aby wyglądał bardziej użytkownika przyjazne – dodawać formuły łącznych, pól nagłówka, formatowania itd. Zapisz zmiany i Prześlij plik do układu planu budżetu przez kliknięcie przycisku Układ &gt;przekazać [![Screenshot26](./media/screenshot26.png)](./media/screenshot26.png)

## <a name="task-6-create-a-budget-planning-process"></a>Zadanie 6: Utwórz proces planowania budżetu
Julia musi utworzyć i aktywować nowy proces planowania budżetu, uwzględniając całą powyższą konfigurację, aby rozpocząć wprowadzanie planów budżetu. Proces planowania budżetu określa, jakie organizacje budżetowania, przepływ pracy, układy i szablony będą używane do tworzenia planów budżetu. 6.1. Przejdź do budżetowania &gt;instalacji &gt;planowania budżetu &gt;proces planowania budżetu i utworzyć nowy rekord.

-   Proces planowania budżetu — budżetowanie DEMF; rok obrachunkowy 2016
-   Cykl budżetu — rok obrachunkowy 2016
-   Księga — DEMF
-   Domyślna struktura konta — Produkcja P&L
-   Hierarchia organizacyjna — pobierz hierarchię utworzoną na początku ćwiczeń
-   Przepływ pracy planowania budżetu — przypisz przepływ pracy automatycznego zatwierdzania dla działu finansów
-   W szablonach i regułach etapu planowania budżetu dla każdego etapu przepływu pracy planowania budżetu określ, czy dozwolone jest dodawanie i modyfikowanie wierszy oraz wybierz układ stosowany domyślnie.

*Uwaga: można tworzyć układy dokumentów dodatkowych i ustawiać tak, aby były dostępne na etapie przepływu pracy planowania budżetu. W tym celu kliknij przycisk Alternatywne układy.* [![Screenshot27](./media/screenshot27.png)](./media/screenshot27.png) 6.2. Wybierz akcje &gt;Uaktywnij, aby aktywować ten przepływ pracy planowania budżetu [![Screenshot28](./media/screenshot28.png)](./media/screenshot28.png)

<a name="exercise-2-process-simulation"></a>Ćwiczenie 2: Symulacja procesu
==============================

## <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>Zadanie 7: Generowanie danych początkowych dla planu budżetu z księgi głównej
7.1. Przejdź do budżetowania &gt;okresowo &gt;Generowanie planu budżetu na podstawie księgi głównej. Wprowadź parametry przetwarzania okresowego i kliknij przycisk Generuj. [![Screenshot29](./media/screenshot29.png)](./media/screenshot29.png) 7.2. Przejdź do budżetowania &gt;budżetu planuje znaleźć planu budżetu utworzonych przez proces generowania. [![Screenshot30](./media/screenshot30.png)](./media/screenshot30.png) 7.3. Otwórz szczegóły dokumentu, klikając hiperłącze numeru dokumentu. Plan budżetu jest wyświetlany zgodnie z definicją w układzie utworzone podczas tego laboratorium [![Screenshot31](./media/screenshot31.png)](./media/screenshot31.png)

## <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>Zadanie 8: Utwórz budżet bieżącego roku w oparciu o wartości rzeczywiste w poprzednim roku
W planie budżetu można użyć metody alokacji, aby łatwo skopiować informacje o planie budżetu z jednego scenariusza do drugiego, podzielić je na okresy i alokować do wymiarów. Użyjemy alokacji do utworzenia budżetu na bieżący rok na podstawie wartości rzeczywistych z poprzedniego roku. 8.1. Wybierz wszystkie linie siatki dokumentu planu budżetu i kliknij przycisk Alokacja budżetu [![Screenshot32](./media/screenshot32.png)](./media/screenshot32.png) 8.2. Wybierz metodę alokacji, klucz okresu, scenariuszy źródłowych i docelowych i kliknij pozycję Alokuj 

[![Screenshot33](./media/screenshot33.png)](./media/screenshot33.png)

Wartości rzeczywiste poprzedniego roku zostaną skopiowane do bieżącego roku budżetu i przydzielić je między okresami za pomocą klucza okresu sprzedaż krzywej. 

[![Screenshot34](./media/screenshot34.png)](./media/screenshot34.png)

## <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>Zadanie 9: Korygowanie planu budżetu przy użyciu programu Excel i kończenie pracy nad dokumentem
9.1. Kliknij przycisk Arkusz otworzyć zawartość dokumentu w programie Excel

[![Screenshot35](./media/screenshot35.png)](./media/screenshot35.png)

9.2. Gdy skoroszyt programu Excel zostanie wyświetlony, skoryguj liczby w dokumencie planu budżetu i kliknij przycisk Publikuj.

[![Screenshot36](./media/screenshot36.png)](./media/screenshot36.png)

9.3. Wróć do dokumentu planu budżetu w usłudze Dynamics 365 dla operacji. Kliknij przycisk przepływu pracy &gt;przesłać do automatycznego zatwierdzania dokumentu

[![Screenshot37](./media/screenshot37.png)](./media/screenshot37.png) 

Po ukończeniu przepływu pracy, etap dokumentu planu budżetu zmienia się na zatwierdzone. [![Screenshot38](./media/screenshot38.png)](./media/screenshot38.png)

<a name="appendix"></a>Dodatek
========

### <a name="auto-approve-workflow-configuration"></a>Konfiguracja przepływu pracy automatycznego zatwierdzania

A. Budżetowanie &gt;instalacji &gt;planowania budżetu &gt;przepływów pracy budżetowania Tworzenie nowego przepływu pracy przy użyciu szablonu przepływów pracy planowania budżetu:

[![Screenshot39](./media/screenshot39.png)](./media/screenshot39.png)

Ten przepływ pracy będzie zawierać tylko jedno zadanie — etap planu budżetu przejścia 

[![Screenshot40](./media/screenshot40.png)](./media/screenshot40.png) 

Zapisz i Uruchom przepływ pracy. 

B. Przejdź do budżetowania &gt;instalacji &gt;planowania budżetu &gt;Konfiguracja planowania budżetu. W karcie etapy tworzenia etapy 2 – wstępne i przesłane 

[![Screenshot41](./media/screenshot41.png)](./media/screenshot41.png)

C. Przejdź do budżetowania &gt;instalacji &gt;planowania budżetu &gt;Konfiguracja planowania budżetu. W karcie etapów przepływu pracy umożliwia skojarzenie przepływu pracy Auto-Zatwierdzanie utworzonego w kroku z fazy początkowej i przesłane 

[![Screenshot42](./media/screenshot42.png)](./media/screenshot42.png)  


